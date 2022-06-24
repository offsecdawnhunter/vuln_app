pipeline {
  agent any
    environment {
      // SEMGREP_BASELINE_REF = "master"

      // SEMGREP_APP_TOKEN = credentials('3bd67de5-9bcc-4fc4-bf25-0467b45f8482')
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
          // sh 'rm -rf $HOME/vuln_app'
					// sh 'cd $HOME && git clone https://github.com/offsecdawn/vuln_app.git && cd vuln_app && git clone https://github.com/returntocorp/semgrep-rules.git && docker run --rm -v "${PWD}:/src" returntocorp/semgrep semgrep --config "/src/semgrep-rules/php"'
          sh 'semgrep ci --config "auto"' 
      }
    }
  }
}