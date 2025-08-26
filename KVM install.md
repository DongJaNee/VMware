# KVM Ubuntu install 하는 방법
## 1. 가상화 지원 여부 확인 
```
sudo apt update
sudo apt install cpu-checker
kvm-ok
```

아래와 같이 출력이 되면 가상화 지원 가능 
```
INFO : /dev/kvm/exists
KVM acceleration can be used
```

## 2. 패키지 설치
```
sudo apt install -y qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virtinst virt-manager
```

## 3. 정상작동 확인

버전 확인 
```
kvm --version
```

실행 확인
```
sudo systemctl is-active libvirtd

active
```

사용자 계정 "libvirt" 및 "kvm" 그룹에 추가 
```
sudo usermod -aG libvirt $USER
sudo usermod -aG kvm $USER
```

## 4. VM 생성 및 실행 
```
sudo virt-manager
```

KVM에서 우분투 22.04 LTS 인스턴스 시작 
```
sudo virt-install --name ubuntu-guest --os-variant ubuntu22.04 --vcpus 2 --ram 2048 --location http://ftp.ubuntu.com/ubuntu/dists/focal/main/installer-amd64/ --network bridge=virbr0,model=virtio --graphics none --extra-args='console=ttyS0,115200n8 serial'
```

**참고 자료**
- https://young-cow.tistory.com/86


