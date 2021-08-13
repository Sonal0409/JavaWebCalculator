pipeline{
    
     tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    agent any
    stages{
        stage('checkout'){
            steps{
               git 'https://github.com/Raghava510/JavaWebCalculator.git'
            }
        }
         stage('Compile'){
              
              steps{
                  echo 'compiling..'
                  sh 'mvn compile'
	      }
          }
          stage('UnitTest'){
               
              steps{
                  sh 'mvn test'
              }
               post {
               success {
                   junit 'target/surefire-reports/*.xml'
               }
           }	
          }
          stage('Package'){
        
              steps{
                  sh 'mvn package'
              }
          }
          
}
}
