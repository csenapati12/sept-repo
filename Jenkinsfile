node(){
    properties([[$class: 'JiraProjectProperty'], [$class: 'DatadogJobProperty', tagFile: '', tagProperties: ''], gitLabConnection('gitlab'), parameters([string(defaultValue: 'master', description: 'Please select the branch  to build your code', name: 'BRANCHNAME', trim: false)])])
    stage('cloning'){
        echo "cloning"
        checkout([$class: 'GitSCM', branches: [[name: '*/$BRANCHNAME']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'a14b9e5e-a271-40ee-be77-eb6595ff5342', url: 'https://github.com/csenapati12/java-tomcat-maven-example.git']]])
    }
    stage('building'){
        echo "building"
        sh label: '', script: 'mvn package'
    }
    stage('nexus upload'){
        echo "nexus upload"
    }
    stage('create docker container'){
        echo "Docker"
    }
    stage('Sonar analysis'){
        echo "sonar"
        
    }
     stage('Dockerverification'){
        echo "Docker verification"
         
     }
  
}
