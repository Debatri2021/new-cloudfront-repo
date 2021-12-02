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
            withAWS(region:'ap-south-1',credentials:'aws_root') {
               // s3Upload(bucket:"bhabani-1997-bhera", file:'firstfolder/index.html');
              s3Upload(bucket:"bhabani-1997-bhera", file:'index.html' );
              s3Upload(bucket:"bhabani-1997-bhera", file:'styles.css' );
              
            }
      }
    }
    
  }
}
