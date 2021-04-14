pipeline {
     agent {label 'node1'}
     stages {
          stage("Checkout") {
               steps {
                    git url: 'https://github.com/kyrene1004/springboot-gradle-sample.git'
               }
           }
           stage("Build") {
               steps {
                    sh "./gradlew clean build"
               }
           }
           stage("Unit test") {
               steps {
                    sh "./gradlew test"
               }
           }
           stage("Deploy to /tmp") {
               steps{
                script{
                        sh "mv sample-springboot-gradle-pipeline/build/libs/springboot-sample-app-0.0.1-SNAPSHOT.jar /tmp/springboot-sample-app-0.0.1-SNAPSHOT.jar"
                }
              }
          }

   }
}