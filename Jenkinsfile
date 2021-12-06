//def ReleaseDir = "c:\inetpub\wwwroot"
pipeline {
			agent any
			stages {
				stage('Git Checking'){
					steps{
						echo "Checking out from Git"
						git 'https://github.com/satishpwr/HelloWorld.git'
					}
				}
				stage('Build') {
    					steps {
						echo "Building the project"
    					    bat "\"${tool 'MSBuild'}\" HelloWorld.sln /p:DeployOnBuild=true /p:DeployDefaultTarget=WebPublish /p:WebPublishMethod=FileSystem /p:SkipInvalidConfigurations=true /t:build /p:Configuration=Release /p:Platform=\"Any CPU\" /p:DeleteExistingFiles=True /p:publishUrl=c:\\inetpub\\wwwroot"
    					}
				}
			}
}
