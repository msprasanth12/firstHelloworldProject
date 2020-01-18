pipeline 
{
	agent any
	stages
	{
		stage('git')
		{
			steps
			{
				git branch: 'master', url: 'https://github.com/msprasanth12/firstHelloworldProject.git'
			}
		}
		stage('maven')
		{
			steps
			{
				bat label: '', script: 'mvn clean'
                bat label: '', script: 'mvn install'
			}
		}
		stage('tomcat')
		{
			steps
			{
				deploy adapters: [tomcat8(credentialsId: 'tomcat-credential', path: '', url: 'http://3.91.59.33:9999/')], contextPath: 'hippo-app', war: '**/*.war'
			}
		}
	}
}
