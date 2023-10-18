
pipeline{
    agent any 
    stages{
        stage("Code")
        {
            steps{
                echo "pulling code from github"
                git url:"https://github.com/adnann-rasheed/fivea.git",branch:"master"
            }
        }
        stage("Copy folder/files to the server"){
            steps{
                sh "sudo cp -r /var/lib/jenkins/workspace/laravel-app/* /var/www/fivea-app"
                sh "cd /var/www/fivea-app && composer du"
                sh "cd /var/www/fivea-app && php artisan view:clear"
            }
        }
    }
}
