pipeline {
	agent {label 'karthi'}
    stages {
        stage ('checkout') {
            steps {
		checkout scm
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn -f java-sample-app/pom.xml clean install' 
	    }
        }
	     stage ('copy') {
            steps {
                sh 'rm -rf /chef-repo/cookbooks/tomcat/files/*' 
                sh 'mv /home/zippyops/jenkins/workspace/chef-project/java-sample-app/target/* /chef-repo/cookbooks/tomcat/files' 
	    }
        }
    }
}
