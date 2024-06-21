pipeline {
    agent {
        label {
            label 'Slave-2'
            customWorkspace "/mnt/test"
    }
    }
    stages {
        stage ('Maven') {
            steps {
                dir ("/mnt/test/") {   
                sh 'sudo yum install maven -y'
                sh 'rm -rf /root/.m2/' 
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
        stage ("Tomcat") {
            steps {
                dir ("/root/server") {
                sh 'wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.90/bin/apache-tomcat-9.0.90.zip'
                sh 'unzip apache-tomcat-9.0.90.zip'
                sh 'rm -rf apache-tomcat-9.0.90.zip'
                sh 'chmod -R 777 *'    
        
    }
}
        }
    }
}        
    
