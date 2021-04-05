pipeline {
    agent {
        label '!windows'
    }

    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }

    stages {
        stage('Build') {
            steps {
                echo "Database engine is ${DB_ENGINE}"
                echo "DISABLE_AUTH is ${DISABLE_AUTH}"
                sh 'printenv'
            }
        }
    }
    post {
        always {
            mail to: 'anshulgarg.88@gmail.com',
                 subject: "Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Build URL ${env.BUILD_URL}"
        }
}
}
