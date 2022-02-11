pipeline{
    agent any
    parameters{
        string(name:'SPEC',defaultValue:"cypress/integration/**/**",description: "Enter the script path that you want to execute")
        choice(name:'BROWSER',choises:['chrome', 'edge','firefox'],description: "Choise the browser where you want to execute your scripts")
    }
    stages{
        stage('Building'){
            steps{
                bat 'echo Building the application'
            }
        }
        stage('Testing'){
            steps{
                bat 'npm i'
                bat 'npx cypress run --browser ${BROWSER} --spec ${SPEC}'
            }
        }
        stage('Deploying'){
            steps{
                echo 'Deploy the application'
            }
        }
    }
}