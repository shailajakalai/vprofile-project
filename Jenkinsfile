pipeline{
    agent
    tools{
        maven 'local_maven'
    }
    stages{
        stage ('Build'){
            steps{
                sh 'mvn clean package'
            }
            post{
                success{
                    echo "Archiving the Artifacts"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to tomcat server') {
            steps{
                deploy adapters: [tomcat9(credentialsId: 'c702e954-b620-42ff-b002-578f3b4318fd', path: '', url: 'http://18.183.33.122:9980/')], contextPath: null, war: '**/*.war'
                echo "Deployment"
            }
        }
    }
}
