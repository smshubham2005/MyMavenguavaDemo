pipeline {
	agent any
		tools{
			maven 'MAVEN'
			}
			
			stages{
			stage('Checkout'){
				steps{
					git branch: 'master' , url: 'https://github.com/smshubham2005/MyMavenGuavaDemo.git'
					}
				}
				
				stage('Build'){
				steps{
					sh ' mvn clean package'
					}
				}
				
				stage('Test'){
				steps{
					sh ' mvn test'
					}
				}
				
				stage('Run Application'){
				steps{
					sh ' mvn exec:java -Dexec.mainClass="com.example.App" '
					}
				}
			}
			
			post{
				success{
					echo ' Build and Deployment successful'
				}
				failure{
					echo ' Build failed '
				}
			}
		}
