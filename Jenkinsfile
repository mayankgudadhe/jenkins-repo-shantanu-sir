pipeline {
    agent {
        label {
            label 'built-in'
            customWorkspace "/mnt/test"
    }
    }
    tools {
        maven "apache_maven"
    }
    stages {
        stage ('Compile Stage') {

            steps { 
                dir ("/mnt/test/jenkins-repo-shantanu-sir/") {
                
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
