# VMware vSphere Hypervisor (ESXi) 설치 가이드

## 목차
- [1. ISO 파일 다운로드](#1-iso-파일-다운로드)
- [2. 부팅 가능한 USB 만들기](#2-부팅-가능한-usb-만들기)
- [3. ESXi 설치하기](#3-esxi-설치하기)
- [4. 네트워크 설정](#4-네트워크-설정)
- [5. 원격 관리 연결](#5-원격-관리-연결)
- [6. ESXi 호스트 클라이언트 설정](#6-esxi-호스트-클라이언트-설정)
- [7. 가상 머신 실행](#7-가상-머신-실행)

## 1. ISO 파일 다운로드
1. [Broadcom 지원 사이트](https://support.broadcom.com/group/ecx/free-downloads)에 접속합니다.
2. VMware vSphere Hypervisor(ESXi) ISO 파일을 다운로드합니다.
   ![VMware 다운로드 페이지](https://github.com/user-attachments/assets/0a0c970f-c295-4d24-9578-653e31f2981c)

## 2. 부팅 가능한 USB 만들기
1. Rufus 프로그램을 실행합니다.
2. 다운로드한 ESXi ISO 파일을 선택합니다.
3. 대상 USB 드라이브를 선택합니다.
4. "시작" 버튼을 클릭하여 부팅 가능한 USB를 생성합니다.

## 3. ESXi 설치하기
1. 생성한 USB를 서버에 연결합니다.
2. 서버를 부팅하고 USB에서 부팅되도록 BIOS 설정을 변경합니다.
3. ESXi 설치 마법사를 따라 진행합니다:
   - 설치 위치(로컬 디스크) 선택
   - 키보드 레이아웃 선택
   - 관리자 암호 설정
   - 설치 확인 및 진행

## 4. 네트워크 설정
1. 설치가 완료되면 F2 키를 눌러 시스템 구성으로 들어갑니다.
2. "Configure Management Network" 선택:
   - IP 구성: 정적 IP 설정
   - IP 주소 입력
   - 서브넷 마스크 입력
   - 기본 게이트웨이 입력
   - DNS 서버 설정
   - 호스트 이름/도메인 설정
3. 설정을 저장하고 네트워크를 재시작합니다.

※ 참고 영상: [ESXi 설치 가이드](https://www.youtube.com/watch?v=dmvJzt5CVqc)

## 5. 원격 관리 연결
1. 다른 PC에서 웹 브라우저를 열고 주소창에 ESXi 서버의 IP 주소 또는 도메인 이름을 입력합니다.
   - 예: `https://your-esxi-ip/` 또는 `https://your-domain/`
2. ESXi 호스트 메인 화면이 표시됩니다.
   ![ESXi 메인 화면](https://github.com/user-attachments/assets/d1359ce0-d570-47ec-a757-5539ab324f84)

## 6. ESXi 호스트 클라이언트 설정
1. 사용자 이름(기본값: root)과 설치 시 설정한 암호로 로그인합니다.
2. 왼쪽 메뉴에서 다양한 관리 옵션을 선택할 수 있습니다:
   - **가상 시스템**: VM 생성 및 관리
   - **스토리지**: 데이터스토어 관리 및 ISO 파일 업로드
   - **네트워킹**: 가상 스위치 및 포트 그룹 설정
   - **호스트**: 시스템 전반 설정
   ![ESXi 호스트 클라이언트](https://github.com/user-attachments/assets/3533f7b3-9247-48dd-9b8e-613433023335)

## 7. 가상 머신 실행
1. 가상 머신을 생성하고 필요한 설정을 완
