#!groovy

def execute
fileLoader.withGit('https://github.com/aur-atomica-net/jenkins-pipeline.git', 'master', null, '') {
    execute = fileLoader.load('docker/execute');
}

execute {
    environment = 'atomica/arch-devel:latest'
    mainScript = '''
makepkg --force --noconfirm --syncdeps --install --nocheck
'''
    postScript = '''
'''
}
