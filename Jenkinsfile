pipeline {
agent any
options {
skipStagesAfterUnstable()
}
stages {
stage('Remove container atual') {
steps {
sh 'docker stop webserver'
sh 'docker container rm -f /root/src/my_php'
}
}
stage('Roda novo Container') {
steps {
sh 'docker run -d --name my_php -p 8888:80 php:7.2-apache'
}
}
stage('Copia PHP para o container'){
steps {
sh 'docker container cp my_php/* my_php:/var/www/html'
}
}
}
}
