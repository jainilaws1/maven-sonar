pipeline
{
	agent any
	stages
	{
		stage ('scm checkout')
		{
			steps
			{
				git branch: 'master', url: 'https://github.com/jainilaws1/maven-project'
			}
		}
		stage ('sonar-check')
		{
			steps
			{
				withMaven (jdk: 'AWS JDK' , maven: 'AWS Maven')
				{
					withSonarQubeEnv('sonar') 
						{
							sh 'mvn clean sonar:sonar package'
						}
				}
			}
		}
	}
}
