pipeline{
agent any
tools{
nodejs "NodeJS 20"
}
stages{
stage("Build"){
steps{
sh 'npm install'
sh 'npm run build"
}
}
stage('Test'){
steps{
sh 'npm test'
}
}
stage('staging Deployment')
{
when{
branch 'main'
}
steps{
sh 'npm run deploy-staging'
}
}
stage('Approval'){
when{
branch 'main'
}
steps{
input messsage:'Approve deployement to production?',ok 'Deploy'
}
}
stage('Production Deployment'){
when{
branch 'main'
}
steps{
sh 'npm run deploy-production'
}
}
}
}
