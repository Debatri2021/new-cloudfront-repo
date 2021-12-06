pipeline {
  agent {
    node {label  'master'}
}
  stages {
    stage('cloning git')
    {
      steps{
        checkout scm
      }
     }
    
    
    
    stage('Deploy') {
            steps {
                echo 'Deploying....'
                withCredentials([[ $class: 'AmazonWebServicesCredentialsBinding',
                                    credentialsId: "aws_root_new",
                                    //accessKeyVariable: 'AWS_ACCESS_KEY_ID',
                                    //secretKeyVariable: 'AWS_SECRET_ACCESS_KEY'
                                    ]]) {}
                                    echo "Removing all files on bucket"
                    bat 'aws s3 ls s3://bhabani-1997-bhera --recursive --human-readable --summarize'
            }
    }
                    
    
    
    
    /*
    stage('Upload file to S3') {
      steps{
        withCredentials([
          [$class: 'AmazonWebServicesCredentialsBinding', credentialsId: 'aws_root']
        ]) {
          script {
            echo "Starting upload in S3"
            bat "dir"
            bat "aws s3 sync ./build/ s3://bhabani-1997-bhera"
            //sh "aws s3 dir s3://bhabani-1997-bhera"
            echo "finished Uploading"
          }
        }
      }
    }  */
    
    
    
    
    
    
    
    
    
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
