pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDk8"
    }

    environment {
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "DevOps157!"
        RELEASE_REPO = "vprofile-release"
        CENTRAL_REPO = "vpro-maven-central"
        NEXUSIP   = "192.168.1.153"
        NEXUSPORT = "8081"
        NEXUS_GRP_REPO = "vpro-maven-group"
        NEXUS_LOGIN = "nexuslogin"
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }

        }
    }
}
