#!/usr/bin/env groovy
//used for IDE 

/*	first pipeline
node{
	echo "hello, World!"
}
*/
// Declarative pipeline "Second Pipeline //
/* 
pipeline {
agent any
stages 
{
	stage('Build') 
	{
		steps 
		{
			echo 'Building..'
		}
	}
	stage('Test') 
	{	
		steps 
		{
			echo 'Testing..'
		}
	}
	stage('Deploy') 
	{
		steps 
		{
			echo 'Deploying....'
		}
	}
}
}*/
// Script //
/*
node 
{
	stage('Build') 
	{
		echo 'Building....'
	}
	stage('Test') 
	{
		echo 'Testing....'
	}
	stage('Deploy') 
	{
		echo 'Deploying....'
	}
}
*/

// Declarative, Third Pipeline, using UNIX based shell commands //
pipeline {
agent any
stages {
stage('Build') {
steps {
sh 'make' 
archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
}
}
}
}
// Script //
node {
stage('Build') {
sh 'make' 
archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
}
}
