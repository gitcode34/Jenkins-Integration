node('master') {
    stage("Fetch Source Code") {
        git 'https://github.com/gitcode34/Jenkins-Integration.git'
    }
    
    dir('.') {
        printMessage('Running Pipeline')
        
        stage("Testing") {
            sh 'python test_functions.py'
        }
        
        stage("Deployment") {
            if (env.BRANCH_NAME == 'master') {
                printMessage('Deploying the master branch')
            } else {
                printMessage('No deployment configiuration for this branch')
                
            }
        }    
        
        printMessage('Pipeline Complete')
    }
}

def printMessage(message) {
    echo "${message}"
}
