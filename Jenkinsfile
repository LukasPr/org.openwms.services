#!groovy

node {
   def mvnHome
   stage('Preparation') {
      git 'git@github.com:spring-labs/org.openwms.services.git'
      mvnHome = tool 'M3'
   }
   stage('Build') {
      sh "'${mvnHome}/bin/mvn' clean package -U"
   }
   stage('Publish') {
      sh "git push heroku master"
   }
   stage('Results') {
      archive 'target/*.jar'
   }
}