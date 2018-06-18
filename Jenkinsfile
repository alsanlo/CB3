pipeline {
  agent any
  stages {
    stage('Preparacion') {
      steps {
        git(url: 'https://desreposrv.goldcar.es:8443/scm/ic/pricing_repo.git', branch: '*/develop')
      }
    }
    stage('Ejecucion') {
      steps {
        bat 'activator.bat clean packageAll'
      }
    }
    stage('Tratamiento') {
      steps {
        archiveArtifacts 'target/*.zip'
      }
    }
  }
}