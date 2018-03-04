pipeline {
   agent any
   stages {
      stage('Build') {
         steps {
            timestamps {
                sh './gradlew'
            }
         }
      }
   }
}