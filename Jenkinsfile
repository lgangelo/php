pipeline {
agent any
options {
skipStagesAfterUnstable()
}
stages {
stage('Remove container atual') {
steps {
sh 'docker stop my_php'
sh 'docker container rm -f my_php'
}
}
stage('Roda novo Container') {
steps {
sh 'docker run -d --name my_php -p 8888:80 php:7.2-apache'
}
}
stage('Copia PHP para o container'){
steps {
sh 'docker cp my_php:/var/lib/jenkins/workspace/jekins_docker/index.php /var/www/html'
}
}
}
}
