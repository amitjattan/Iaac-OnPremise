node {

    stage ('checkout') {

        echo "- - - - Checkout Code - - - -"
	checkout scm
    }

    stage ('setupenv') {
    	echo " - - - - Setting up environment now - - - - "
	}

    stage ('Vagrant') {
    
    echo " - - - - Ready to execute Vagrant now - - - - "
    bat 'vagrant up'
    echo " - - - - - - C O M P L E T E D - - - - - - - "
    }
}
