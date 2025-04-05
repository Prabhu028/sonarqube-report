pipeline {
    agent any 
    
    tools{
        maven 'maven3'
    }
    stages{
        
        stage("Git Checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/jaiswaladi246/Petclinic.git'
            }
        }
        stage("Sonarqube Analysis "){
            steps{
                    sh "mvn clean package"           
                    sh ''' mvn sonar:sonar -Dsonar.url=http://ip_address:9000/ -Dsonar.login= token \
                    -Dsonar.projectName=Petclinic \
                    -Dsonar.java.binaries=. \
                    -Dsonar.projectKey=Petclinic '''
    
                }
            }
        }
    }
