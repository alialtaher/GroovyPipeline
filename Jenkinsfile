#!/usr/bin/env groovy
//used for IDE 


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
