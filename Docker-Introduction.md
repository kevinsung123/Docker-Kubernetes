#### Docker란?
 - 컨테이너 기술을 사용하여 애플리케이션의 실행 환경을 구축 및 운용하기 위한 플랫폼
 - 애플리케이션의 실행에 필요로한 것을 하나로 모아 Docker이미지를 관리함으로써 이식성을 높임
 
 1. **컨테이너 기술의 개요**
	- 컨테이너란 ?
		- Host OS상에 논리적인 구획(컨테이너)을 만들고, 애플리케이션을 작동시키기 위해 필요한 라이브러리나 애플리케이션을 하나로 모아, 마치 별도의 서버처럼 제공
		- Host OS의 리소스를 논리적으로 분산, 여러개의 컨테이너가 공유
		- 오버헤드가 적고 가볍다
		- 애플리케이션의 실행환경을 모음으로써, 이식성을 높이고 portable, 확장성이 좋은 환경 지향
			```
			※ 오버헤드 : 가상화를 수행하기 위해 필요한 CPU,Memory,Disk등 사용량
			※ 서버가상화 기술
				- 호스트형 서버 가상화 
					- oracle의 VM VirtualBox,
					- VMware의 VMware Workstation Player
				- 하이퍼바지어형 서버 가상화
					- Host OS없이 HW를 직접제어 자원을 효율적 이용
					- 단, 가상환경마다 별도의 OS가 작동하므로 가상환경 시작에 걸리는 오버헤드 단점
					- Microsoft Windows Server의 Hyper-V
					- Citrix의 XenServer
			```
![enter image description here](https://www.docker.com/sites/default/files/d8/styles/large/public/2018-11/container-what-is-container.png?itok=vle7kjDj)

 2. **컨테이너의 역사**
	  1. FressBSD Jail
			- 오픈소스인 UNIX의 FreeBSD의기술
   			- 2000년에 FreeBSD 4.0에서 도입
    		- 특징 			
		    		1. 프로세스 구획화 			
		    		2. 네트워크 구획화 			
		    		3. 파일시스템 구획화
   		2. Solaris Container
		   	- Oracle의 상용 UNIX인 Solaris에서 사용하는 컨테이너 기술
		   	- 2005년에 release된 Solaris10에 추가된 기능
			- 특징
				1. Solaris 존 : 하나의 OS공간을 가상적으로 분할하여 여러OS가 작동하는것처럼 SW 파티셔닝기술
				2. Solaris 리소스매니저
	  2. Linux Container(LXC)
		  - Linux상에서 사용하는 컨테이너 환경을 LXC
		  - Linux커널의 컨테이너 기능을 이용하기 위한 툴이나 API제공
		  - **namespace와 cgroups**라는 리소스 관리 장치를 사용하여 분리된 환경 제공 
		  - 특정 디렉토리를 루트 디렉토리로 변경하는 chroot를 사용하여 분리환경 만듬
		  - Docker이전버전에서는 LXC사용, 현재버전은 미사용

####  참고
- CNCF(Cloud Native Computing Foundation) 
	- 클라우드 네이티브 컴퓨팅을 추진하는 조기
	- 2016년 Linux Foundation으로부터 정식 발족
	- 컨테이너 오케스트레이션 툴인 kubernetes
	- 모니터링을 하는 Prometheus
	- 로그수집하는 Fluetnd
	- 컨테이너 런타임인 container 및 rkt
	- 서비스 디스크버리인 CoreDNS
	- RPC프레임워크인 gRPC
	- 위를 포함하는 16개 프로젝트를 관리
	- 성숙도	
		- Inception
		- Incubating
		- Graduated
	- Docker는 물론 Google, Mircrosoft, Amazon 등과 같은 주요 퍼블릭 클라우드 업체를 플래티넘 넘버로
	- Red Hat, VMWare, IBM, Intel등 많은 기업이 참ㅇ여
	- http://www.cncf.io 
