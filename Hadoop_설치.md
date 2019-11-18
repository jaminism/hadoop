
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
	- sudo apt-get update && upgrade
	- 
						


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM3MzQxMTAwNSwtMTQ3OTYzMzU2MCwtMT
cyMjA3OTYwM119
-->