pipeline{
    agent any

    tools {
        java ('Java_home')
        maven('my maven')
    }
    stages {
        stage ('1checkout'){
            steps {checkout scm
            echo 'code checkout successfully'
        }
        }
        stage ('2 build'){
            steps {
               sh mvn clean compile
            echo 'build completed'
            }
    }
    stage ('3 test'){
        steps{
            sh mvn test
            echo 'test completed'
        }
        }
        stage ('4 package'){
            steps {
                sh 'mvn package'
                echo 'packaged to war'
            }
        }
        stage ('5 deploy'){
            steps {
                sh 'ls -l target/*.war'
                echo 'war file ready for tomcat deployment'
            }
        }
    }
}