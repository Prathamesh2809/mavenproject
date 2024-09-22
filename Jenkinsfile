pipeline
{agent any
stages
{
stage('scm checkout')
{ steps { git branch: 'master', url: 'https://github.com/Prathamesh2809/mavenproject.git' }}


stage('compile the job')    //validate then compile
{steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
   sh 'mvn compile'    // some block
} }}

}
}

