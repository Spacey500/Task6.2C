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
        stage('Test') {
            steps {
                echo "Run Unit Tests using Jenkins"
                echo "Run Integration tests using Jenkins"
            }
            post {
                always {
                    // Save the build log to a file
                    sh 'echo "${BUILD_LOG}" > build.log'
                }
                success {
                    // Send an email with the build log as an attachment
                    emailext to: 'Chelsea.Dore04@gmail.com',
                        subject: 'Build Status Email',
                        body: 'Build was successful!',
                        attachmentsPattern: 'build.log'
                }
                failure {
                    // Send an email with the build log as an attachment
                    emailext to: 'Chelsea.Dore04@gmail.com',
                        subject: 'Build Status Email',
                        body: 'Build failed!',
                        attachmentsPattern: 'build.log'
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo "Integrate a code analysis tool callef PMD"
                echo "Make sure it meets industry standards"
            }
        }
        stage('Security Scan'){
            steps{
                echo "Perfom a security scan using NeuVector"
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo "deploy the application to AWS EC2 instance staging server "
            }
        }
        stage('Intergration Tests'){
            steps{
                echo "run integration tests on staging environments"
                echo "Make sure the application functions as a production-like environment"
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "deploy the application to the AWS EC2 instance production server"
            }
        }
        
    }
}
