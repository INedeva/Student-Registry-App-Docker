pipeline {
    agent any
    stages {
        stage('NPM Install') {
            steps {
                bat 'npm install'
            } 
        }
        // stage('Parallel') {
        //     parallel {
        //         stage('Run npm audit tests') {
        //             steps {
        //                 bat 'npm audit'
        //             } 
        //         }
        //         stage('Execute tests') {
        //             steps {
        //                 bat 'npm test'
        //             } 
        //         }
        //     }
        // }
        stage('Execute tests') {
            steps {
                bat 'npm test'
            } 
        }
        stage('Deploy to staging') {
            steps {
                echo 'Deploy to staging'
            } 
        }
        stage('Approval for Production Deployment') {
            steps {
                input message: 'Approve deployment to production?', ok: 'Deploy'
            } 
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Prod'
            } 
        }
    }
}