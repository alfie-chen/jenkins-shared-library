@Library('jenkins-shared-library@main') _

def tools = new org.devops.tools()

pipeline {
  agent any
  
  parameters { 
    text(name: 'DEPLOY_TEXT', defaultValue: 'One\nTwo\nThree\n', description: '')
    string(name: 'NODE_NAME', defaultValue: 'default-node', description: 'Name of the node to run the job on')
  }
  
  stages {
    stage('Hello') {
      steps {
        echo 'OTAＡＡＡＡＡＡＡＡ!!!!!'
        script {
          tools.PrintMessage("OTAAAAAAAAAAAAA")
        }
      }
    }
  }
}
