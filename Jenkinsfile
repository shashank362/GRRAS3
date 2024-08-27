pipeline{
agent any
parameters {
  choice choices: ['QA', 'UAT', 'DEV'], name: 'ENVIRONMENT'
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
script{
if ( "${env.ENVIRONMENT}" == 'QA' ){
sh 'cp target/GRRAS3.war /home/shashank/extracted/apache-tomcat-9.0.93/webapps'
echo "deployment has been done on QA!"
			 }
else if ( "${env.ENVIRONMENT}" == 'UAT' ){
sh 'cp target/GRRAS3.war /home/shashank/extracted/apache-tomcat-9.0.93/webapps'
echo "deployment has been done on UAT!"
}
echo "deployment has been done!"
                        

}
}
}
}
}
