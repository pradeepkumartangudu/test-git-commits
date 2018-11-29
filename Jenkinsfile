pipeline { 
    agent any 
    stages {
        stage('Build & Deploy') { 
            steps { 
                load "./paramaters.groovy"
                sh 'echo $bucketname'
		sh 'wget -q https://releases.hashicorp.com/terraform/0.11.8/terraform_0.11.8_linux_amd64.zip'
                sh 'unzip -qo terraform_0.11.8_linux_amd64.zip'
                sh '''#!/bin/bash -l
						echo "test script"
		pwd
                ls ./ -al
		pwd
		
		
			wget -q https://releases.hashicorp.com/packer/1.3.1/packer_1.3.1_linux_amd64.zip
            unzip -qo packer_1.3.1_linux_amd64.zip
            ./packer build -var aws_access_key=$access_key -var aws_secret_key=$secret_key packer.json			
			rm -rf ./* ./.git	
'''
            }
        }
    }
}
