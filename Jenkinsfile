pipeline {
	agent any
	parameters {	
		choice(name: 'VAGRANT', choices: ['up', 'halt', 'status'], description: 'Pick something')
		choice(name: 'VM', choices: ['kubemaster', 'kubenode01'], description: 'Pick something')
	}
	stages { 
	    stage('Checkout') {
		  steps {
		   git branch: 'master',
		       credentialsId: 'GITHUB',
		       url: 'https://github.com/Muralit20/Vagrant-VMS.git'
		  }
	    }
	    stage('src') {
			steps {
			sh "cp -rf /var/lib/jenkins/workspace/Vagrant-VM/* /mnt/c/Users/Lenovo/vagrant-workspace/Vagrant-VMS"
			}
		}
        stage('VM') {
			agent { 
			    label {
			        label 'WIN' 
			        customWorkspace 'C:\\Users\\Lenovo\\vagrant-workspace\\dev'
			    }    
			}
            steps {
                script {
					powershell """
					cd ..\\Vagrant-VMS
					.\\pshell.ps1 ${params.VAGRANT} ${params.VM}"""
                } 
            }
        }
    }
}