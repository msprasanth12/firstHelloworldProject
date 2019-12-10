pipeline 
{
	agent any
	stages
	{
		stage('git')
		{
			steps
			{
				git branch: 'test', credentialsId: 'tomcat-credential', url: 'https://github.com/msprasanth12/firstHelloworldProject.git'
			}
		}
		stage('maven')
		{
			steps
			{
				bat label: 'abc', script: 'mvn clean'
                bat label: 'cba', script: 'mvn install'
			}
		}
		stage('tomcat')
		{
			steps
			{
				deploy adapters: [tomcat8(credentialsId: 'tomcat-credential', path: '', url: 'http://localhost:8888/')], contextPath: 'hippo-app', war: '**/*.war'
			}
		}
	}
}
