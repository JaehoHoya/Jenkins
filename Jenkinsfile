pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                echo 'Cloning Git repository...'
                def GITHUB_REPO = "https://github.com/JaehoHoya/Jenkins.git"

                checkout([
                    $class: 'GitSCM',
                    branches: [[name: 'main']],
                    userRemoteConfigs: [[
                        credentialsId: 'gitLogin', // Jenkins에서 등록한 GitHub Credentials ID
                        url: GITHUB_REPO
                    ]]
                ])
                
                echo "Git repository cloned successfully!"
                sh "ls -al ."  // 디버깅: 파일 확인용
            }
        }
    }
}
