pipeline {
    agent any

    parameters {
        string(name: 'branch', defaultValue: 'main', description: 'Branch to build')
    }

    triggers {
        cron('0 3 * * 1-5')
    }

    stages {
        stage('SCM'){
            steps {
                git branch: "${params.branch}", url: 'https://github.com/unkas444/jenkins-pipelines.git'
            }
        }
        stage('build'){
            steps {
                echo 'Build the code'
            }
        }
        stage('Package'){
            when {
                expression {
                    return params.branch == 'release'
                }
            }
            steps {
                echo 'Packing the code for release'
            }
        }
    }
}