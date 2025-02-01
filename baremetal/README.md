config for bare metal server

## TODOs
- 3.jenkins-helm-setup 에서 jenkins-pv를 사용하도록 설
    - 현재 KinD 설정이 worker node 3개여서, hostPath를 이용하기 위해서는 추가로 nodeSelector 설정이 필요해 보임.

## 3.jenkins-helm-setup.sh
### script 실행 전
- `export DOCKER_USERNAME=<docker hub id>`, `export DOCKER_PASSWORD=<docker hub personal access token`

### script 실행 후
- JenkinsLocation의 URL을 실제 접속한 URL로 변경해주어야 한다.
- pipeline script: `git branch: 'main', credentialsId: 'github-token', url: 'https://github.com/hsacog/blog'`
    - Jenkins 설정의 Credentials 에서, Kind는 `Username with password`, Username은 `github id`, Password는 `github PAT`, ID는 `github-token` 으로 설정해서 생성한다.

## Jenkins
### JDK 21 설치
Amazon corretto를 사용하면 된다. (`https://docs.aws.amazon.com/corretto/latest/corretto-21-ug/downloads-list.html`)

Dashboard > Jenkins 관리 > Tools
JDK installations > Add JDK
Install automatically 에 체크
Download URL for binary archive: `https://corretto.aws/downloads/latest/amazon-corretto-21-aarch64-linux-jdk.tar.gz`
Subdirectory of extracted archive: `amazon-corretto-21.0.6.7.1-linux-aarch64`

