@Library('locus-common') _

pipeline{
    agent any
    stages{
        stage('Demo'){
            steps{
                trial("Anandita Sahu")
                script{
                    calculator.add(20,10)
                    calculator.sub(20,10)
                    calculator.mul(20,10)
                    calculator.div(20,10)
                }
            }
        }
    }
    
    post {

    // Email Ext plugin:
    success {

      emailext (
          subject: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: """<p>SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
            <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""",
          to: "${emailRecipient}",
          from: "buildNotifications@emailaddress.com"
        )
    }

    failure {

      emailext (
          subject: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: """<p>FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
            <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""",
          to: "${emailRecipient}",
          from: "buildNotifications@emailaddress.com"
        )
    }
  }
}
