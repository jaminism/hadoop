
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
		`$ sudo vu /etc/hosts`
		
		`127.0.0.1 localhost`
		`192.168.100.101 master`
		`192.168.100.102 slave1`
		`192.168.100.103 slave2`
		`192.168.100.104 slave3`

	- hostname 변경
		`$ sudo vi /etc/hostname`
		master, slave1, slave2, slave3
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjM4NjIzNDc1LDEzNzM0MTEwMDUsLTE0Nz
k2MzM1NjAsLTE3MjIwNzk2MDNdfQ==
-->