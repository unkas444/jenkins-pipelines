pipeline {
    agent any
    parameters {
        string(name: 'branch', defaultValue: 'main', description: 'Branch to build')
    }

    stages {
        stage('SCM'){
            steps {
                git branch: "${params.branch}", url: 'https://github.com/unkas444/jenkins-pipelines.git'
            }
        }
        stage('parallel phases'){
            parallel{
                stage('static analysis'){
                    steps {
                        echo 'Performing static analysis'
                        sleep time: 3, unit: 'SECONDS'
                        echo 'Static analysis complete'
                    }
                }
                stage('build and test'){
                    stages{
                        stage('build'){
                            steps {
                                echo 'Building the code'
                                sleep time: 3, unit: 'SECONDS'
                                echo 'Build complete'
                            }
                        }
                        stage('unit test'){
                            steps {
                                echo 'Executing unit tests'
                                sleep time: 3, unit: 'SECONDS'
                                echo 'Unit tests complete'
                            }
                        }
                    }
                }
            }
        }
        stage('Package'){
            steps {
                echo 'Packing the code for release'
            }
        }
    }
}