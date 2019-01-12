pipeline {
	agent {label 'gayu'}
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
                sh 'mv /home/zippyops/jenkins/workspace/chef-project/java-sample-app/target/*.war chef-repo/cookbooks/tomcat/files' 
	    }
        }
    }
}
