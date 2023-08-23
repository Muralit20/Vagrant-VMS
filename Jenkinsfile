pipeline {
	agent { 
			    label {
			        label 'WIN' 
			        customWorkspace 'C:\\Users\\Lenovo\\vagrant-workspace\\dev'
			    }    
			}
	parameters {	
		choice(name: 'VAGRANT', choices: ['up', 'halt', 'status'], description: 'Pick something')
		choice(name: 'VM', choices: ['kubemaster', 'kubenode01','kubenode02'], description: 'Pick something')
	}
	stages { 
	    stage('Checkout') {
		  steps {
		   powershell "git clone https://github.com/Muralit20/Vagrant-VMS.git"
		  }
	    }
    }
}
