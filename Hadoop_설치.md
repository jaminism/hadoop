
## Overview
- 하둡 에코 시스템의 환경을 구성하기 위해 하둡을 설치하고 기타 컴포넌트인 Hive, Oozie, Spark 등을 설치한다. 

## 시스템 구성
- OS는 Ubuntu 18.04.3
- NameNode 1대, DataNode 3대(Sencondary NM 1대) 구성
- 스케줄러는 Oozie
- MetaDB는 mariaDB
- YARN 을 이용한 클러스터 메모리 관리
- 데이터 프로세스는 Hive

### 설치
1. VirtualBox 를 통한 우분투 설치. (Master)
2. 기본 환경 설정

	`sudo apt-get update && upgrade`
	`sudo add-apt-repository ppa:webupd8team/java `
	`sudo apt-get update && sudo apt-get install -y build-essential python oracle-java8-set-default wget vim`

3. 자바 확인
	  `$ java -version`
						
4. 네트워크 설정
	- master : 192.168.100.101
	  slave1 : 192.168.100.102
	  slave2 : 192.168.100.103
	  slave3 : 192.168.100.104
	  
		
	- 위의 설정값 입력
		`$ sudo vi /etc/hosts`
		
		`127.0.0.1 localhost`
		`192.168.100.101 master`
		`192.168.100.102 slave1`
		`192.168.100.103 slave2`
		`192.168.100.104 slave3`

	- hostname 변경
		`$ sudo vi /etc/hostname`
		master, slave1, slave2, slave3
		
5. 그룹 추가
	`$ sudo vi adduser --ingroup hadoop hduser`
	
	`$ sudo vi /etc/sudoers`
	`# User privilege specification
	root	ALL=(ALL:ALL)	ALL`
	- 여기 하위에 hduser를 추가한다.
	` hduser	ALL=(ALL:ALL)	ALL`	

6. 공개 키 생성
	`apt-get install openssh-server`
	설치 후
	`ssh-keygen -t rsa -P ""`
	입력 뒤에 엔터를 두번~ 하면 .ssh 폴더에 id_rsa.pub 파일이 생성된다.
	.ssh폴더에 autohrized_keys 파일을 복사한다.
	`cat .ssh/id_rsa.pub >> .ssh/authorized_keys`

7. 재부팅
	재부팅 한번 해준다.
	`reboot`
	만약 권한때문에 안되면 sudo reboot

8. 하둡 설치
	[https://hadoop.apache.org/releases.html](https://hadoop.apache.org/releases.html) 에서 하둡 다운로드 >> 2.9.2 버전을 링크 주소 복사해서 wget 으로 받았다. 
	`wget http://apache.mirror.cdnetworks.com/hadoop/common/hadoop-2.9.2/hadoop-2.9.2-src.tar.gz`

9. 압축 해제
	
	 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc3NDc5MDA5OCwtNDA3ODU3NTQxLDYzOD
YyMzQ3NSwxMzczNDExMDA1LC0xNDc5NjMzNTYwLC0xNzIyMDc5
NjAzXX0=
-->