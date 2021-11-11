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
  options { disableConcurrentBuilds() }
  tools{
    maven 'maven'
  }

  parameters {
    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
    text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
    booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
    choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
  }

  environment {
    DEMO_URL = "google.com"
    SSH = credentials('CENTOS_SSH')
  }

  stages {
    stage('one') {
      environment {
        DEMO_URL = "YAHOO.com"
      }
      steps {
        sh '''
          echo ${DEMO_URL}
          echo ${SSH_USR}
          echo ${PERSON}
        '''
      }
    }
    stage('compile') {
      input {
        message "Should we continue?"
        ok "Yes, we should."
        //submitter "alice,bob"
        //parameters {steps{
            //string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')  sh 'mvn clean'
      //}
      }
      steps{
        sh 'mvn clean'
      }
    }
    stage('Three') {
      steps{
        echo 'Three'
      }
    }
  }

}