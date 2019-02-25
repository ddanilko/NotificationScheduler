pipeline {
  agent any
  stages {
    stage('Build RAM') {
      steps {
        echo 'Build RAM'
      }
    }
    stage('Build FullHI Image') {
      steps {
        echo 'Build FullHi Image'
      }
    }
    stage('Smoke Tests') {
      steps {
        echo 'Smoke Tests'
      }
    }
    stage('Essential Tests') {
      parallel {
        stage('Hardware A Tests') {
          steps {
            echo 'Hardware A Tests'
          }
        }
        stage('Hardware B Tests') {
          steps {
            echo 'Hardware B Tests'
          }
        }
        stage('Hardware C Tests') {
          steps {
            echo 'Hardware C Tests'
          }
        }
        stage('Hardware D Tests') {
          steps {
            echo 'Hardware D Tests'
          }
        }
      }
    }
    stage('Full Tests') {
      when { branch 'master' }
      parallel {
        stage('Hardware A Tests') {
          steps {
            echo 'Hardware A Tests'
          }
        }
        stage('Hardware B Tests') {
          steps {
            echo 'Hardware B Tests'
          }
        }
        stage('Hardware E Tests') {
          steps {
            echo 'Hardware E Tests'
          }
        }
      }
    }
    stage('Should Release?') {
      when { branch 'master' }
	  steps {
        echo 'Release'
      }
    }
  }
}