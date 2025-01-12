pipeline
{
agent any
stages
{
 stage('scm checkout: download code from github')
 {steps { git branch: 'master', url: 'https://github.com/Nikunj8421/simple-java-maven-app.git'  }}


 stage('execute unit test framework')
 {steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA', maven: 'Maven-3.9.9', mavenSettingsConfig: '', traceability: true) {
    sh 'mvn test'
} } }


 stage('generate artifact')
 {steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA', maven: 'Maven-3.9.9', mavenSettingsConfig: '', traceability: true) {
    sh 'mvn clean -B -DskipTests package'
} } }

 stage('deploy to tomcat')
{ steps { sshagent(['DevCICD'])
  { sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/Maven-Project/target/my-app-1.0-SNAPSHOT.jar ec2-user@13.126.84.79/:/usr/share/tomcat/webapps'  } } }
  

}
}
