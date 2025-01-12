pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
                git 'https://github.com/Nikunj8421/mavenproject.git'
            }
        }
        stage('Validate the Job') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA', maven: 'Maven', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn validate'
                }
            }
        }
        stage('Compile the Job') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA', maven: 'Maven', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn compile'
                }
            }
        }
        stage('Build the Job') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA', maven: 'Maven', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn clean -B -DskipTests package'
                }
            }
        }
    }
}
