pipeline 
{
 	agent any
 	stages 
 	{
 		stage ('Build Application')
 		{
 			steps
 			{
 			echo 'Build Application ...'
 			bat 'mvn clean install'
 			}	
		 }
		 
		 
 		stage ('Deploy Application to Mulesoft CloudHub')
 		{
 		environment
 			{
 				ANYPOINT_CREDENTIALS = credentials('anypointPlatform')
 			}
 				steps
 				{
 				echo 'Deploying to Sandbox environment...'	
 				bat 'mvn package deploy -DmuleDeploy'
 				}
 		}
 	}
}