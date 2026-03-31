pipeline {
    agent any
    tools {
        maven "maven3914"
        jdk "jdk17"
    }
    
    environment {
        SNAP_REPO = 'vprofile-snapshot'
		NEXUS_USER = 'admin'
		NEXUS_PASS = 'd05af764-da99-4fc3-a1f3-763936a6fffc'
		RELEASE_REPO = 'vprofile-release'
		CENTRAL_REPO = 'vprofile-maven-central'
		NEXUSIP = '172.31.69.15'
		NEXUSPORT = '8081'
		NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}