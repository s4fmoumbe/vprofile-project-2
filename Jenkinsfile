pipeline {
    agent any
    tools {
        maven "MAVEN3.9"
        jdk "JDK17"
    }

    environment {
        SNAP_REPO = 'app-snapshot'
                NEXUS_USER = 'admin'
                NEXUS_PASS = 'DevOps157/'
                RELEASE_REPO = 'app-release'
                CENTRAL_REPO = 'app-proxy'
                NEXUSIP = '192.168.1.111'
                NEXUSPORT = '8788'
                NEXUS_GRP_REPO = 'app-group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post {
                success {
                    echo "Now Archiving."
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
}    
