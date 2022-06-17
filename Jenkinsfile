pipeline{
    agent any
    stages{
        stage('CopyArtifact1'){
            steps{
                sh 'ls'
                sh 'pwd'
                sh 'tar -jcvf SAM_Binary.tar.bz2 *'
                archiveArtifacts artifacts: '*.html', followSymlinks: false
                sh 'ls'
            }
        }
        stage('CopyArtifact2'){
            steps{
                echo "This is CopyArtifact2"
                sh 'ls'
                copyArtifacts filter: '*.bz2', projectName: 'CopyArtifacts1', selector: lastSuccessful(), target: 'CopyArtifact2'
                sh 'ls'
            }
        }
    }
}
