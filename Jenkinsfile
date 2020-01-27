pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'gradle build'
        bat 'gradle javadoc'
        archiveArtifacts 'build/docs/javadoc/**'
        archiveArtifacts 'build/libs/*.jar'
        junit 'build/test-results/test/*.xml'
      }
    }

    stage('Mail Notification') {
      steps {
        mail(subject: 'Push Github', body: 'Your project have been pushed to the github repo', to: 'gn_farah@esi.dz')
      }
    }

  }
}