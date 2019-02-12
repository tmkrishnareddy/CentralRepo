pipeline{
     agent any
            stages{
                 stage('one'){
                      steps{
                       echo "Build has been executed successfully"
                      }
                 }     
                 stage('two'){
                      steps{
                        input ('Do you want to proceed?')
                        echo "test has been executed successfully"
                      }
                 }
                 stage('three'){
                      steps {
                         echo "Deploy has been executed successfully"
                      }
                 }
                 stage('four'){
                      parallel {
                           stage('unit test'){
                                steps{
                                echo "Running unit test"
                                }
                           }
                           stage('Integration step'){
                                agent{
                                     docker{
                                               reuseNode false
                                               image 'ubuntu'                                     
                                     }
                                }
                                steps{
                                echo "Running the integration test"
                                }
                           }
                    
                      }
                 }
     }     
}
