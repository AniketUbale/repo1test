pipeline {
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt/repo-1"
        }
    }
    
    stages{
        stage('delete'){
            steps{
                sh "rm -rf /mnt/repo-1/*"
            }
        }
        stage('clone'){
            steps{
                git 'https://github.com/AniketUbale/repo1test.git'
            }
        }
        stage('deploy'){
            steps{
                sh "yum install httpd -y"
                sh "service httpd start"
                sh "cp -r /mnt/repo-1/index.html /var/www/html/"
                sh "chmod -R 777 /var/www/html/index.html"
            }
        }
    }
}
