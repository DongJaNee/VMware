# VMware Workstation 설치 가이드

## 1. 파일명 정확히 확인하기
먼저, 해당 디렉토리에서 **파일 목록**을 확인하여 정확한 파일명을 확인합니다.

```bash
ls
```

여기서 `VMware-Workstation-Full-17.6.3.x86_64.bundle` 파일이 정확하게 나타나는지 확인하세요. 파일명이 다를 수 있으니 확인 후 다음 단계를 진행합니다.

## 2. 실행 권한 확인 및 부여
파일명이 정확한지 확인한 후, **실행 권한을 다시 한 번 부여**합니다:

```bash
chmod +x VMware-Workstation-Full-17.6.3.x86_64.bundle
```

## 3. 설치 실행
이제 **`sudo`**로 실행해 보세요. 정확한 파일명이 맞는지 다시 한 번 확인한 후, 아래 명령어로 실행합니다:

```bash
sudo ./VMware-Workstation-Full-17.6.3.x86_64.bundle
```

## 4. VMware 실행
설치가 완료된 후, 아래 명령어로 VMware Workstation Pro를 실행할 수 있습니다:

```bash
vmware
```

## 5. RHEL VM 설정 권장사항
Red Hat Enterprise Linux VM 생성 시 권장 설정:

* **CPU**: 4~8 코어
* **메모리**: 8GB 이상
* **디스크**: 50GB 이상
