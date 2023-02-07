node
{
def mavenHome = tool name: "maven3.8.7"
stage('CheckOutcodefromGitRepo')
{
git branch: 'Development', credentialsId: 'bbf7d210-e299-42db-9582-03e60568898e', url: 'https://github.com/ElamathiN/maven-web-application.git'
}
stage('BuildPackage')
{
sh "${mavenHome}/bin/mvn clean package"
}
stage('GenerateSonarReport')
{
sh "{mavenHome}/bin/mvn sonar:sonar"
}
stage('UploadArtifactintoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}
}
