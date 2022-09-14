pipeline{
     agent any 
     stages{
          stage('One'){
               steps{
                    echo 'Hello'
               }
          }
          stage('Two'){
               steps{
                    input('Do you want to proceed')
               }
          }
          stage('Three'){
                    when{
                         not{
                              branch 'main'
                         }
                    }
               steps{
                    echo "Hello"
               }
          }
          stage('Four'){
               parallel{
                    stage('Unit-test'){
                         steps{
                              echo "running the unit test"
                         }
                    }
                    stage('Integration test'){
                         agent{
                              docker{
                                   image 'ubuntu'
                              }
                         }                               
                        steps{
                              echo 'Running the integration unit test'
                         }
                    }
               }
          }
     }
}


                    
             
  
