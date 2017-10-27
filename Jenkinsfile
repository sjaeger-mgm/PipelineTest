node {
    stage 'Checkout', {
        	echo "Checking out $Globals.SCM_URL/master"
            checkout scm
    }

    stage 'Build', {
        echo 'Start building app'
        sh './gradlew build'
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