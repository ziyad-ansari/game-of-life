pipeline {
    agent any
    stages {
        stage ('vcs') {
            steps {
                git url: "https://github.com/ziyad-ansari/game-of-life.git", 
                    branch: 'dev'
            }
            
        }
        stage ('build') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
