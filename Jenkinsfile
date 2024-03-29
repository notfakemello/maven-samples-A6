pipeline {
  agent any
  tools { 
      maven 'DHT_MVN' 
      jdk 'DHT_SENSE' 
  }
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/notfakemello/maven-samples-A6', branch: 'master')
      }
    }

    stage('run') {
      steps {
	sh 'git bisect start'
	sh 'git bisect good 98ac319'
	sh 'git bisect bad 1986446'
	sh 'git bisect run mvn clean test'
	sh 'git bisect reset'
      }
    }

  }
}
