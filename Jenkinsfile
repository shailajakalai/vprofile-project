node{
    
    stage('Clone repo'){
        git branch: 'vp-rem', credentialsId: '2095b32c-e96f-499c-9d38-edadfb98da21', url: 'https://github.com/shailajakalai/vprofile-project.git'
    }
    stage('Maven Build'){
        def mavenHome = tool name: "maven-3.8.6", type: "maven"
        def mavenCMD = "${mavenHome}/bin/mvn"
        sh "${mavenCMD} clean package"
    }
}
