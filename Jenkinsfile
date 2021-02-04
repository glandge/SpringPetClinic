pipline{
    agent{label "master"}
    tools{maven 'M3'}
    stages{
        stage('checkout'){
            steps{
                git branch : 'main', url: "https://github.com/glandge/SpringPetClinic.git"
            }
        }
        stage('Build'){
            steps{
                sh "mvm compile"
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar var/lib/jenkins/workspace/PetClinincDeclarativePipeline/target/*.jar'
            }
        }
    }
}
