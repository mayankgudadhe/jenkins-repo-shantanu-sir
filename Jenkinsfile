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
                //sh 'sudo chmod -R 777 /root/server'
                dir ("/mnt/test/") {   
                sh 'sudo yum install maven -y'
                sh 'sudo rm -rf /root/.m2/' 
                }
            }
        }
        stage ('Compile Stage') {

            steps { 
                dir ("/mnt/test/") {
                
                    sh 'sudo mvn clean package'
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
                dir ("/mnt/server") {
                sh 'sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.90/bin/apache-tomcat-9.0.90.zip'
                sh 'sudo unzip apache-tomcat-9.0.90.zip'
                sh 'sudo rm -rf apache-tomcat-9.0.90.zip'
                sh 'sudo chmod -R 777 *'    
        
    }
}
            
        }
        stage ("Tomcat") {
            dir ("/mnt/server/apache-tomcat-9.0.90/bin/") {
                sh 'cp -r /mnt/test/target/jenkins-example-1.0-SNAPSHOT.jar /mnt/server/apache-tomcat-9.0.90/webapps
                sh './startup.sh'
            
    }
}        
    
