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
}
