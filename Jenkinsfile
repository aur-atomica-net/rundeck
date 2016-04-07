#!groovy

def execute
fileLoader.withGit('https://github.com/aur-atomica-net/jenkins-pipeline.git', 'master', null, '') {
    execute = fileLoader.load('docker/execute');
}

execute {
    environment = 'atomica/arch-devel:latest'
    docker_arguments="-u 999:999"
    mainScript = '''
sudo -u build makepkg --force --noconfirm --syncdeps --install --nocheck
'''
    postScript = '''
'''
}
