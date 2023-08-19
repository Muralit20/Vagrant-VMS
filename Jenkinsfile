pipeline {
	agent {
		node {
			label 'WIN'
			customWorkspace 'C:\\Users\\Lenovo\\vagrant-workspace\\dev'
		}
	}
	parameters {	
		choice(name: 'VAGRANT', choices: ['up', 'halt', 'status'], description: 'Pick something')
		choice(name: 'VM', choices: ['kubemaster', 'kubenode01'], description: 'Pick something')
	}
	stages { 
	    stage('Checkout') {
		  steps {
		   git branch: 'master', credentialsId: 'GITHUB', url: 'git@github.com:Muralit20/Vagrant-VMS.git'
		  }
	    }
	    stage('src') {
		  steps {
		   powershell "cp .\\pshell.ps1 C:\\Users\\Lenovo\\vagrant-workspace\\github\\certified-kubernetes-administrator-course"
		  }
	    }
        stage('VM') {
            steps {
                script {
		 powershell "cd C:\\Users\\Lenovo\\vagrant-workspace\\github\\certified-kubernetes-administrator-course",
		 powershell ".\\pshell.ps1 ${params.VAGRANT} ${params.VM}"
                } 
            }
        }
    }
}
