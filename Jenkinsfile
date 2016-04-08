#!groovy

def makepkg
fileLoader.withGit('https://github.com/aur-atomica-net/jenkins-pipeline.git', 'master', null, '') {
    makepkg = fileLoader.load('docker/makepkg');
}

makepkg {}
