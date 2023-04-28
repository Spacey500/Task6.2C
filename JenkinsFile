pipeline{
    agent any
    environment{
        DIRECTORY_PATH="/Desktop/School Year2/223/5.1"
        TESTING_ENVIRONMENT="Testing Environment1"
        PRODUCTION_ENVIRONMENT= "Chelsea" 
    } 
    stages{
        stage('Build'){
            steps{
                echo "Use Maven to build the code, compile, and package the code"
            }
        }
        stage('Test'){
            steps{
                echo "Run Unit Tests using Jenkins"
                echo "Run Intergrations tests using Jenkins"
            }
        }
        stage('Code Analysis'){
            steps{
                echo "Analyse"
            }
        }
        stage('Security Scan'){
            steps{
                echo "deploy the application to a testing environment specified by the environment variable, $TESTING_ENVIRONMENT "
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo "deploy the application to a testing environment specified by the environment variable, $TESTING_ENVIRONMENT "
            }
        }
        stage('Intergration Tests'){
            steps{
              timeout(time: 10, unit: "SECONDS"){
                sleep 5
            }
            }

        }
        stage('Deploy to Production'){
            steps{
                echo "deploy the code to the production environment, $PRODUCTION_ENVIRONMENT"
            }
        }
        
    }
}