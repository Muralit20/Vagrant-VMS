pipeline {
	agent any
	parameters {	
		choice(name: 'VAGRANT', choices: ['up', 'halt', 'status'], description: 'Pick something')
		choice(name: 'VM', choices: ['kubemaster', 'kubenode01','kubenode02'], description: 'Pick something')
	}
	stages { 
	    stage('Checkout') {
		  agent { 
			    label {
			        label 'WIN' 
			        customWorkspace 'C:\\Users\\Lenovo\\vagrant-workspace\\dev'
			    }    
			}
		  steps {
		   git branch: 'master',
		       credentialsId: 'GITHUB-S',
		       url: 'https://github.com/Muralit20/Vagrant-VMS.git'
		  }
	    }
    }
}
