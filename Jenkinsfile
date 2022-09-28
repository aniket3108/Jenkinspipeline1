pipeline{
    
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
//Agent section is mandatory   
    agent any
    
    stages{
        
        stage('Clone the Repo')
        {
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        
        stage('Compile the code')
        {
            steps{
            sh 'mvn compile'
            }
        }
        
        stage('Code review')
        
        {
            steps
            {
            sh 'mvn pmd:pmd'
            }
        }
        
        stage ('Unit Testing')
        {
            steps{
            sh 'mvn test'
            }
        
        
        post{
            success{
                junit 'target/surefire-reports/*.xml'
                
            }
        }
        }
        
        stage('Package')
        {
            steps{
                sh 'mvn package'
            }
        } 
        
        stage('Deploy')
        {
            steps{
                echo 'Deploy Code'
            }
        }
        
       }
    
        }
        
