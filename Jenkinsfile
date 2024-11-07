pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
        checkout scm
      }
    }
    
    stage("Test"){
      steps{
        nodejs('Node'){
          echo 'Testing application .....'
          sh 'npm install'
          sh 'npm test'
        }
        
      }
    }
    
    stage("Build"){
      steps{
        nodejs('Node'){
          echo 'Testing application .....'
          sh 'npm install'
          sh 'npm run build'
        }
        
      }
    }

    stage("Build Image"){
      steps{
        sh 'docker build -t my-node-app:1.0 .'
      }
    }
  }
}
