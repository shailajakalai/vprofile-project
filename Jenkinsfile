node{
    
    stage('Clone repo'){
        git branch: 'main', credentialsId: '3e747781-b5bf-4386-8794-f76f36cbd8c0', url: 'https://github.com/shailajakalai/iv.git'
    }
    stage('Maven Build'){
        def mavenHome = tool name: "maven-3.8.6", type: "maven"
        def mavenCMD = "${mavenHome}/bin/mvn"
        sh "${mavenCMD} clean package"
    }
}
