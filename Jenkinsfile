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
				deploy adapters: [tomcat8(credentialsId: 'tomcat-credential', path: '', url: 'http://localhost:8888/')], contextPath: 'hippo-app-010', war: '**/*.war'
			}
		}
	}
}
