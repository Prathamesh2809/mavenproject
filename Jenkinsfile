pipeline
{agent any
stages
{
stage('scm checkout')
{agent { label 'JAVA' }
   steps { git branch: 'master', url: 'https://github.com/Prathamesh2809/mavenproject.git' }}


stage('compile the job')    
{agent { label 'JAVA' }
   steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
   sh 'mvn compile'    
} }} 

stage('execute a unit test framework')    
{agent { label 'JAVA' }
   steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
   sh 'mvn test'    
} }}

stage('Build the code')    
{agent { label 'JAVA' }
   steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
   sh 'mvn clean -B -DskipTests package'    
} }}

// stage('Push the code to tomcat server')
// { steps{ sshagent (credentials: ['DEVCICD']) {
//     sh 'scp -o StrictHostKeyChecking=no /webapp/target/webapp.war ec2-user@172.31.22.148:/usr/share/tomcat/webapps/'
//   }}
// }

// stage('deploy to tomcat')
// { steps { sshagent(['TOMCATCICD'])
//   { sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.30.204:/usr/share/tomcat/webapps'  } } }


}
}

