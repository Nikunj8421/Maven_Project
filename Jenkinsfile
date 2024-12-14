pipeline{
    agent any
    stages{
        stage ('scm checkout')
        {steps{git 'https://github.com/Nikunj8421/mavenproject.git'}}

        stage ('validate the job')
        {steps{withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA', maven: 'Maven', mavenSettingsConfig: '', traceability: true) {
            sh 'mvn validate'
}}}
    }
}
