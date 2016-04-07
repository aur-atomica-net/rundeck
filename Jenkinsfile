#!groovy

stage 'Load files from GitHub'
def standardBuild
fileLoader.withGit('https://github.com/aur-atomica-net/jenkins-pipeline.git', 'master', null, '') {
    standardBuild = fileLoader.load('standardBuild');
}

stage 'Run standardBuild'
standardBuild {
    environment = 'docker.artfire.me/arch-devel:latest'
    mainScript = '''
uname -a
'''
    postScript = '''
ls -l
'''
}
