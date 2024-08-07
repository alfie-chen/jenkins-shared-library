@Library('jenkins-shared-library@main') _

def tools = new org.devops.tools()
hello()

pipeline {
  agent any
  
  parameters { 
    text(name: 'DEPLOY_TEXT', defaultValue: 'One\nTwo\nThree\n', description: '')
    string(name: 'NODE_NAME', defaultValue: 'default-node', description: 'Name of the node to run the job on')
  }
  
  stages {
    stage('Hello') {
      steps {
        echo 'Hello World!!!!!'
        script {
          tools.PrintMessage("Print Message", 'green')
        }
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: '''
        Log/**,
        *.log,
        can_log.txt,
        can_api.log,
        report/environment.properties
      ''', allowEmptyArchive: true

      junit allowEmptyResults: true, testResults: 'result.xml'
      allure includeProperties: false, jdk: '', results: [[path: 'report']]

      emailext mimeType: 'text/html',
      body: '''${SCRIPT, template="groovy-html-larry-refactor.template"}''',
      postsendScript: '$DEFAULT_POSTSEND_SCRIPT',
      presendScript: '$DEFAULT_PRESEND_SCRIPT',
      replyTo: '$DEFAULT_REPLYTO',
      subject: '''
        Hello Subject!!!!
      ''',
      to: '''
        alfie.feifei@gmail.com
      '''
    }
  }
}

