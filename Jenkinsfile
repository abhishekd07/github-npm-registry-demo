node {

    def PAT
    
    withCredentials([string(credentialsId: 'GH-PAT', variable: 'GHPAT')]) {
    
        PAT = "$GHPAT"
        bat("echo $PAT")
    }

    stage('Checkout') { // for display purposes
      // Checkout code from GitHub repository
      git branch: 'main', 
      url: "https://$PAT@github.com/abhishekd07/github-npm-registry-demo.git
   }
   
    stage('Npm Install') {   
        bat 'npm install' 
        }
  
    stage('Npm Publish') { 
        bat ("echo //npm.pkg.github.com/:_authToken=$PAT  > .npmrc")
        bat 'npm publish' 
    }
}
