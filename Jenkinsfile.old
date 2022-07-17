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
/*
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
*/
// Script //
/*
node {
stage('Build') {
sh 'make' 
archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
}
}
*/


// Declarative //
pipeline {
agent any
stages {
stage('Test') {
steps {
/* `make check` returns
* using `true` to allow
*/
sh 'make check || true'
junit '**/target/*.xml'
}
}
}
}
// Script //
node {
/* .. snip .. */
stage('Test') {
/* `make check` returns non-zero on test failures,
* using `true` to allow the Pipeline to continue nonetheless
*/
sh 'make check || true' 
junit '**/target/*.xml' 
}
/* .. snip .. */
}
