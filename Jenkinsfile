pipeline {
    agent any

    stages {
        stage ('GetProject') {
            steps {
                git 'https://github.com/grifinmi/first_test_with_GIT.git'
            }
        }
        stage ('build') {
            steps {
                sh 'mvn clean:clean'
                sh 'mvn dependency:copy-dependencies'
                sh 'mvn compiler:compile'
            }
        }
//         stage ('Exec') {
//             steps {
//                 sh 'mvn exec:java'
//             }
//         }
        stage ('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            archiveArtifacts allowEmptyArchive: true,
                artifacts: '**/ct5171_first_test_with_git*.jar'
        }
    }
}
