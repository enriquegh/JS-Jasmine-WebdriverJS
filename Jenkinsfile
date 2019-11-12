node {
    env.NODEJS_HOME = "${tool '8.16'}"
    env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
    stage('Checkout Repo') {
    git branch: 'latest-browsers', changelog: false, poll: false, url: 'https://github.com/enriquegh/JS-Jasmine-WebdriverJS.git'
    
    }
    stage('Install') {
        sh 'npm --version'
        sh 'node --version'
        sh 'npm install'
    }
    stage('Run tests') {
        sauce('c19998b0-da3d-474f-b008-ffe93a928c72') {
          sauceconnect() {
            sh 'npm test'
          
          }
        }
    }
}