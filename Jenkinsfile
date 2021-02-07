pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('CheckOut'){
            steps{
                git branch: 'main', url:'https://github.com/Sumitcz97/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('test'){
            steps{
                sh 'mvn test'
            }
            
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePiepLine/target/*.jar'
            }
        }
    }
}
