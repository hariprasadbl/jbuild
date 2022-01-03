pipeline {
			agent slave2 
			stages {
				stage('BUILD') {
					steps {
						sh '''
							cd /opt/jenkins/workspace/pipeline
							mvn clean install
						'''
					}
				}
				stage('TEST1') {
					steps {
						sh 'echo "fist test stage in Jenkinsfile"'
					}	
				}
				stage('TEST2') {
					steps {
						sh 'echo "Second test stage in Jenkinsfile"'
					}	
				}
				stage('DEPLOY') {
					steps {
						sh '''
					          scp /opt/jenkins/workspace/pipeline/target/works-with-heroku-1.0.war ec2-user@18.221.223.72:/tomcat/webapps
                              ssh ec2-user@18.221.223.72 'tomcatup'	
						
						
						'''
					}
				}
			}
		}
