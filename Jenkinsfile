pipeline {
    agent {
        label {
            label 'Slave-1'
            customWorkspace "/mnt/test"
    }
    }
    stages {
        stage ('Git') {
            steps { 
                sh 'sudo yum install git -y'
            }
        }
        stage ('Maven') {
            steps {
                dir ("/mnt/test/") {
                sh 'sudo yum install maven -y'
                }
            }
        }
        stage ('Compile Stage') {

            steps { 
                dir ("/mnt/test/") {
                
                    sh 'mvn clean package'
                }
            }
            
        }
        
        stage ('Echo Branch') {

            steps {
                
                    echo "This is master branch"
                }
            
        }
    }
}
