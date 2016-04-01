#!groovy

stage 'Load files from GitHub'
def environment, helloworld
fileLoader.withGit('https://github.com/aur-atomica-net/jenkins-pipeline.git', 'master', null, '') {
    standardBuild = fileLoader.load('standardBuild');
}

stage 'Run standardBuild'
standardBuild.run {
    environment = 'golang:1.5.0'
    mainScript = '''
go version
'''
    postScript = '''
ls -l
'''
}
