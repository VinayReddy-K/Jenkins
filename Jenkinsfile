//pipeline {
//
////agent {
////  //node { label 'Workstation-1' }
////  //label 'JAVA'
////  none
////}
//  agent any
//
//  stages {
//     stage('Master Node') {
//       agent {
//         label 'MASTER'
//       }
//       steps {
//         sh 'echo hello'
//       }
//     }
//
//     stage('Agent Node') {
//       agent {
//         label 'JAVA'
//       }
//       steps {
//         sh 'echo hello'
//       }
//     }
//  }
//  post {
//
//    always {
//      sh 'echo post stage'
//    }
//  }
//}

// IN BELOW PIPILINE WE R USING ENV SECT.

pipeline {
  agent any

  environment {
    DEMO_URL = "google.com"
  }
  stages {
    stage('one') {
      environment {
        DEMO_URL = "YAHOO.com"
      }
      steps {
        sh 'echo ${DEMO_URL}'
      }
    }
  }

}