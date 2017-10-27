#! /usr/bin/groovy

node('master') {
	def repo = 'https://github.com/chuv2/jenkins.git'

	stage('cleanup') {
		deleteDir()
	}
	
	withCredentials([usernameColonPassword(credentialsId:'chuv2', variable: 'USERPASS')]){
		stage('clone repo') {
			git url: repo
		}
		dir('jenkins') {
//			bat "#!/bin/sh -e\n git remote add my-credentials ${repo.replace('//github.com', '//'+USERPASS.replace('$', '%24') + '@github.com')}"
			bat "git status"
		}
	}
}