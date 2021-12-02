pipeline {
  agent any 
  stages {
    stage('cloning git')
    {
      steps{
        checkout scm
      }
     }
    
    stage('Upload file to S3') {
      steps{
        withCredentials([
          [$class: 'AmazonWebServicesCredentialsBinding', credentialsId: 'aws_root']
        ]) {
          script {
            echo "Starting upload in S3"
            sh "ls -lrt ."
            sh "aws s3 sync . s3://bhabani-1997-bhera"
            sh "aws s3 ls s3://bhabani-1997-bhera"
            echo "finished Uploading"
          }
        }
      }
    }
    
    
    
    
    
    
    
    
    
    /*   stage('Upload file to S3') {
      steps{
            withAWS(region:'ap-south-1',credentials:'aws_root') {
               // s3Upload(bucket:"bhabani-1997-bhera", file:'firstfolder/index.html');
              s3Upload(bucket:"bhabani-1997-bhera", file:'index.html' );
              s3Upload(bucket:"bhabani-1997-bhera", file:'styles.css' );
              
            }
      }
    }
    */
  }
}
