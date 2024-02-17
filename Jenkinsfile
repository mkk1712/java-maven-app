node {
    stage('Git'){
      git 'https://github.com/mkk1712/java-maven-app'      
    }
    
    stage('Maven Build'){
      sh 'mvn clean package'   
    }
    stage('Archive Artifacts'){
         archiveArtifacts 'target/myweb.war'
    }
    
    stage('Email'){
    
    mail bcc: '', body: '''Thanks,
Java Home''', cc: '', from: '', replyTo: '', subject: 'Pipeline Demo', to: 'maheshreddy0421@gmail.com'





    }
}
