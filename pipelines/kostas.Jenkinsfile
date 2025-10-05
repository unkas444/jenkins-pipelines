pipeline {
    agent any

    environment {
        SENTENCE = "hope bla"
    }
    stages {
        stage('Hello'){
            steps {
                echo 'Hello Kosta'

                script {
                    def words = env.SENTENCE.split(' ')

                    for (word in words){
                        echo word
                    }
                }
            }
        }
    }
}