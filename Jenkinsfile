pipeline {
    agent any
    parameters { 
        choice(name: 'BUILD_BRANCH', choices: ['main', 'master'], description: 'build-branch') 
        }
    stages {
        stage ('vcs') {
            steps {
                git url: "https://github.com/ziyad-ansari/game-of-life.git", 
                    branch: "${params.BUILD_BRANCH}"
            }
            
        }
        stage ('build') {
            mail subject: "$JOB_NAME Build_Started",
                 body: "$JOB_NAME Build_Started",
                 to: "ziyadansari333@gmail.com"
            steps {
                sh 'export PATH=/usr/lib/jvm/java-8-openjdk-amd64/bin:$PATH'
                sh 'mvn package'
            }
        }
    }
    post {
        failure {
            mail subject: "$JOB_NAME Build_Failed",
                 body: "$JOB_NAME Build_Failed",
                 to: "ziyadansari333@gmail.com"
        }
    }
}