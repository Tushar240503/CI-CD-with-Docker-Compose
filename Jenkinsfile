#!/usr/bin/env groovy

@Library("Shared")

def gv

pipeline {
    agent any
    tools {
        maven 'maven'
    }
     environment {
          IMAGE NAME ='tushar24sharma/docker:1.1.2-21'
    }
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                    buildJar()
                }
            }
        }
        stage("build and push image") {
            steps {
                script {
                       buildimage 'tushar24sharma/docker:7.1'
                       dockerlogin()
                       dockerpush 'tushar24sharma/docker:7.1'
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }
    }
}

