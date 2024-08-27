pipeline{
agent any
triggers {
  pollSCM '* * * * *'
}
stages{
stage('Checkout'){
steps{
git 'https://github.com/shashank362/GRRAS3.git'
}
}
stage('Build'){
steps{
sh 'mvn install'
}
}
stage('Deploy'){
steps{
sh 'cp target/GRRAS3.war /home/shashank/extracted/apache-tomcat-9.0.93/webapps'
}
}
}
}

