#### Ubuntu 20.04
## packege list Update & Upgrade
sudo apt-get update && sudo apt-get upgrade -y

## took install (Network check, Text editor, Distributed Shell
sudo apt-get install -y net-tools vim pdsh openssh-server

## SSH Join (Without password)
# SSH Create key
ssh-keygen -t rsa -P ""

# 생성된 공개키를 승인된 키 목록(authorized_keys)에 추가
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

# 비번 없이 접속되는지 테스트
ssh localhost

# jdk
sudo apt-get install -y openjdk-8-jdk

# java version check
java -version
openjdk version "1.8.0_452"
OpenJDK Runtime Environment (build 1.8.0_452-8u452-ga~us1-0ubuntu1~20.04-b09)
OpenJDK 64-Bit Server VM (build 25.452-b09, mixed mode)

readlink -f $(which java)
/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java

ls -l /usr/lib/jvm/
total 4
lrwxrwxrwx 1 root root   20  4월 16  2025 java-1.8.0-openjdk-amd64 -> java-8-openjdk-amd64
drwxr-xr-x 7 root root 4096  5월 11 18:18 java-8-openjdk-amd64

# 전역
# sudo vim /etc/environment

# PATH -- 실행 파일(.bin)들의 경로 목록. 어디서든 'java' 명령어를 바로 쓸 수 있게 함.
# PATH="...기존경로...:/usr/lib/jvm/java-8-openjdk-amd64/bin"
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/usr/lib/jvm/java-8-openjdk-amd64/bin"

# JAVA_HOME -- 자바 설치 최상위 경로. 하둡 엔진이 자바를 찾기 위한 필수 기준점.
JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"  

# J2SDKDIR -- Java SDK 경로. 일부 하둡 라이브러리와 개발 도구에서 참조.
J2SDKDIR="/usr/lib/jvm/java-8-openjdk-amd64"  

# J2REDIR -- Java Runtime(JRE) 경로. 자바 실행 환경의 위치를 명시.
J2REDIR="/usr/lib/jvm/java-8-openjdk-amd64/jre"

# DERBY_HOME -- Apache Derby DB 경로. 추후 Hive 메타스토어(DB) 구축 시 사용 예정 (현재 OpenJDK 미포함으로 주석 처리).
#DERBY_HOME="/usr/lib/jvm/java-8-openjdk-amd64/db"
