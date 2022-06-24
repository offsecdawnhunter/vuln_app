pipeline {
  agent any
    environment {
      // SEMGREP_BASELINE_REF = "master"

      SEMGREP_APP_TOKEN = credentials('SEMGREP_APP_TOKEN')
      SEMGREP_REPO_URL = env.GIT_URL.replaceFirst(/^(.*).git$/,'$1')
      SEMGREP_BRANCH = "${GIT_BRANCH}"
      SEMGREP_JOB_URL = "${BUILD_URL}"
      SEMGREP_REPO_NAME = env.GIT_URL.replaceFirst(/^https:\/\/github.com\/(.*).git$/, '$1')
      SEMGREP_COMMIT = "${GIT_COMMIT}"
      SEMGREP_PR_ID = "${env.CHANGE_ID}"

      // SEMGREP_TIMEOUT = "300"
    }
    stages {
      stage('Semgrep-Scan') {
        //  when {
        //     branch "master"
        //   }
        steps {
          // sh 'pip3 install semgrep'
          sh 'semgrep ci --config auto'
      }
    }
  }
}