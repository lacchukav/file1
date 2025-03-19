pipeline{
    agent any
    stages{
        stage{
            steps{
                git url:"https://github.com/lacchukav/file1.git" , branch:"main"
            }
        }
        stage ('dependiency'){
            steps{
                bat '''
                    pyhton -m venv venv
                    call venv\\scripts\\activate
                    python -m pip install --upgrage pip
                    pip install pytest
                    '''

            }
        }
        stage ('test'){
            steps{
                bat '''
                    call venv\\scripts\\activate
                    pytest test.py
                    '''
            }
        }
        stage ('deploy'){
            steps{
                bat '''
                    call venv\\scripts\\activate
                    python adding.py
                    '''

            }
        }
    }
    
}