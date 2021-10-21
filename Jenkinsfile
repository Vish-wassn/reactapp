pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
                sh 'aws s3 cp package.json s3://reactapp21oct2021'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key package.json --acl public-read'
                sh 'aws s3 cp yarn.lock s3://reactapp21oct2021'
                sh 'aws s3api Jenkinsfile --bucket reactapp21oct2021 --key yarn.lock --acl public-read
                sh 'aws s3 cp package.json s3://reactapp21oct2021'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key Jenkinsfile --acl public-read'
                sh 'aws s3 cp .gitignore s3://reactapp21oct2021'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key .gitignore --acl public-read'
                sh 'aws s3 cp public s3://reactapp21oct2021 --recursive'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key public --acl public-read'
                sh 'aws s3 cp public s3://reactapp21oct2021 --recursive'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key public --acl public-read'
                sh 'aws s3 cp .github/workflows s3://reactapp21oct2021 --recursive'
                sh 'aws s3api put-object-acl --bucket reactapp21oct2021 --key .github/workflows --acl public-read'
            }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
