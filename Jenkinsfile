timestamps {
node {
    stage 'Checkout', {
        	echo "Checking out $Globals.SCM_URL/master"
            checkout scm
    }

    stage 'Clean', {
    	echo 'Cleaning Project'
    	sh './gradlew clean'
    }

    stage 'Build', {
    	echo 'Start building app'
 		sh './gradlew build'
    }

    stage 'Package', {
        echo 'Start packaging app'
        sh './gradlew jar'
    }

    stage 'Publish', {
        echo 'Publish docker file'
        sh './gradlew buildDocker'
    }
}

final class Globals implements Serializable {
	private Globals() {}
	static final SCM_USER = 'sjaeger-mgm'
	static final SCM_URL = "https://github.com/sjaeger-mgm/PipelineTest.git" as String
	static final SCM_CREDENTIALS = 'sjager-mgm'
}
}