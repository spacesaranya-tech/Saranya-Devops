pipeline {

    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Stage 1 : Build Started'

                bat 'dir'

                echo 'Project downloaded successfully.'
            }
        }

        stage('Test') {
            steps {

                echo 'Stage 2 : Testing Started'

                script {

                    def content = readFile('hello.txt')

                    if(content.contains("ERROR")){

                        error("Validation Failed : hello.txt contains ERROR")

                    }

                    else{

                        echo "Validation Passed"

                    }
                }
            }
        }

        stage('Deploy') {
            steps {

                echo 'Stage 3 : Deploy Started'

                echo 'Deployment Successful'

            }
        }
    }

    post {

        success {

            echo 'Pipeline Completed Successfully'

        }

        failure {

            echo 'Pipeline Failed'

        }

    }

}
