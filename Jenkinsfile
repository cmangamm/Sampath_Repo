pipeline{
    agent any
    stages{
        stage('CopyArtifact1'){
            steps{
                sh 'ls'
                sh 'pwd'
                sh 'tar -jcvf SAM_Binary.tar.bz2 *'
                archiveArtifacts artifacts: '*tar.bz2', followSymlinks: false
                sh 'ls'
            }
        }
        stage('CopyArtifact2'){
            steps{
                echo "This is CopyArtifact2"
                sh 'ls'
                //copyArtifacts filter: '*.bz2', projectName: 'CopyArtifacts1', selector: lastSuccessful()
                //copyArtifacts filter: '*.bz2', projectName: 'CopyArtifacts1', selector: lastSuccessful()
                copyArtifacts filter: '*.tar.bz2', projectName: 'CopyArtifacts1', selector: lastSuccessful()
                sh 'ls'
            }
        }
    }
}
