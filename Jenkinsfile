pipeline{
    agent any
    stages{
        stage('CopyArtifact1_Stage'){
            steps{
                sh 'ls'
                sh 'pwd'
                sh 'tar -jcvf SAM_Binary.tar.bz2 *'
                archiveArtifacts artifacts: '*.bz2', followSymlinks: false
                sh 'ls'
            }
        }
        stage('CopyArtifact2_Stage'){
            steps{
                echo "This is CopyArtifact2"
                sh 'ls'
                //copyArtifacts filter: '*.bz2', projectName: 'CopyArtifacts1', selector: lastSuccessful()
                //copyArtifacts filter: '*.bz2', projectName: 'CopyArtifacts1', selector: lastSuccessful()
                copyArtifacts filter: '*.bz2', projectName: 'CopyArtifact1', selector: lastSuccessful()
                sh 'ls'
            }
        }
    }
}
