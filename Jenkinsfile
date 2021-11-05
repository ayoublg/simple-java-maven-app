pipeline {

  agent any
  
  tools { 
    maven 'Maven3' 
    jdk 'JDK8' 
  }
  
  stages {
    stage("Initialize") {
      steps {
        sh '''
            echo "PATH = ${PATH}"
            echo "M2_HOME = ${M2_HOME}"
        ''' 
      }
    }
    stage("build") {
      
      steps {
        echo 'building the app..'
        sh 'mvn package'
      }
      
    }
    
    stage("test") {
      
      steps {
        echo 'testing the app..'
        sh 'mvn test'
      }
      
    }
    
    stage("installing") {
      
      steps {
        echo 'deploying the app..'
        sh 'mvn deploy'
      }
      
    }
      
  }
    
}
