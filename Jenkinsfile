pipeline{
    agent any
    parameters{
        string(name:'SPEC',defaultvalue:"cypress/integration/**/**",description: "Enter the script path that you want to execute")
        string(name:'BROWSER',choise:['chrome', 'edge','firefox'],description: "Choise the browser where you want to execute your scripts")
    }
    options{
        ansColor('xterm')
    }
    stages{
        stage('Deploying'){
        echo "Building the application"
        }
        stage('Testing'){
            steps{
            bat "npm i"
            bat "npx cypress run --browser ${BROWSER} --spec ${SPEC}"
            }
        }
        stage('Deploying'){
            echo "Deploy the application"
        }
    }

}