pipeline {
  agent any
    environment {
      // SEMGREP_BASELINE_REF = "master"

      // SEMGREP_APP_TOKEN = credentials('SEMGREP_APP_TOKEN')
      SEMGREP_APP_TOKEN = "ba4673a7f62a1cd1f66812dd49acca3015d2bc9ff6ab4b4f03363a164f4869c4"
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
          sh 'semgrep ci'
          // sh 'echo $SEMGREP_APP_TOKEN'
      }
    }
  }
}