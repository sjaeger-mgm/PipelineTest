node {
    stage 'Checkout', {
        	echo "Checking out $Globals.SCM_URL/master"
            checkout scm
    }
    stage 'Build', {
        echo 'Start building app'
        withMaven(jdk: '9', maven: '3.5.2') {
            sh 'mvn -f "my-app/pom.xml" clean install'
        }
    }

    stage 'Package', {
        echo 'Create jar file'
        withMaven(jdk: '9', maven: '3.5.2') {
            sh 'mvn -f "my-app/pom.xml" package'
        }
    }

    stage 'Deploy', {
        echo 'Fake Deploy'
    }
}

final class Globals implements Serializable {
	private Globals() {}
	static final SCM_USER = 'sjaeger-mgm'
	static final SCM_URL = "https://github.com/sjaeger-mgm/PipelineTest.git" as String
	static final SCM_CREDENTIALS = 'sjager-mgm'
}