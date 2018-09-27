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
    cd "C:/Program Files/Git"
    .\git-bash.exe sh '''
   {
    while read -r line
    do
    	platform=$(echo "$line" |awk -F "," '{ print $1 }')
      version=$(echo "$line" |awk -F "," '{ print $2 }')
      package=$(echo "$line" |awk -F "," '{ print $3 }')
      allowed_port=$(echo "$line" |awk -F "," '{ print $4 }')
      image=$(echo "$line" |awk -F "," '{ print $5 }')
      infra=$(echo "$line" |awk -F "," '{ print $6 }')
      environment=$(echo "$line" |awk -F "," '{ print $7 }')
      removeInfra=$(echo "$line" |awk -F "," '{ print $8 }')
	
	if [ "$infra" = "Y" ];then
  E:\Users\amitk.kmr\.jenkins\workspace\OnPremiseEnviromentProvisioning\vagrant up
		fi
	removeInfra=$(echo "$line" |awk -F "," '{ if ($5=="N") print $10; }')
	echo "$removeInfra"
	if [ "$removeInfra" = "Y" ]; then
  E:\Users\amitk.kmr\.jenkins\workspace\OnPremiseEnviromentProvisioning\vagrant destroy
	fi
    done
    } < E:\Users\amitk.kmr\.jenkins\workspace\OnPremiseEnviromentProvisioning\config.csv
    echo " - - - - - - C O M P L E T E D - - - - - - - "
    
    '''
    }
}
