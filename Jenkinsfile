pipeline {
    agent any
    tools {
        maven "maven3914"
        jdk "jdk17"
    }
    
    environment {
        SNAP_REPO = 'vprofile-snapshot'
		NEXUS_USER = 'admin'
		NEXUS_PASS = '::9d)csx$R2-"Tj'
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
            post{
                success{
                    echo "Archiving in progress"
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Test'){
            steps {
                sh 'mvn -s settings.xml test'
            }

        }

        stage('Checkstyle Analysis'){
            steps {
                sh 'mvn -s settings.xml checkstyle:checkstyle'
            }
    }
}