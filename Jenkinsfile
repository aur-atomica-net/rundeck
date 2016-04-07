#!groovy

def execute
fileLoader.withGit('https://github.com/aur-atomica-net/jenkins-pipeline.git', 'master', null, '') {
    execute = fileLoader.load('docker/execute');
}

execute {
    environment = 'atomica/arch-devel:latest'
    docker_arguments="-u 0:0 -e HOST_USER_ID=$(id -u) -e HOST_USER_GID=$(id -g)"
    mainScript = '''
sed -i -e "s/^build:\([^:]*\):[0-9]*:[0-9]*/build:\1:${HOST_USER_ID}:${HOST_USER_GID}/"  /etc/passwd
sed -i -e "s/^build:\([^:]*\):[0-9]*/build:\1:${HOST_USER_GID}/"  /etc/group
sudo -u build makepkg --force --noconfirm --syncdeps --install --nocheck
'''
    postScript = '''
'''
}
