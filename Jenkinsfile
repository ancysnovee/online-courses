pipeline{
    stages{
        stage('clone repo'){
            steps{
                git credentialsId : '', url : 'https://github.com/ancysnovee/online-courses.git', branch : 'main'
            }
        }
        stage('dependency'){
            steps{
                bat '''
                python -m venv venv
                call venv\\Scripts\\activate
                pthon -m pip install --upgrade pip
                pip install pytest
                '''
            }
        }
        stage('test'){
            steps{
                bat '''
                call venv\\Scripts\\activate
                python test.py
                '''
            }
        }
        stage('deploy'){
            steps{
                bat '''
                call venv\\Scripts\\activate
                python available.py
                '''
            }
        }
    }
}