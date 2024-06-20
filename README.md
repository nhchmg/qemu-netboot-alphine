# qemu-netboot-alphine
boot alphine from network

#file download https://dl-cdn.alpinelinux.org/alpine/edge/releases/aarch64/netboot/
#              https://dl-cdn.alpinelinux.org/alpine/edge/releases/armv7/netboot/

#wget https://dl-cdn.alpinelinux.org/alpine/edge/releases/armv7/netboot/vmlinuz-lts

#wget https://dl-cdn.alpinelinux.org/alpine/edge/releases/armv7/netboot/initramfs-lts

# The console argument is required to get console output


#arm

qemu-system-arm \
  -M virt -m 256M -cpu cortex-a15 \
  -kernel vmlinuz-lts -initrd initramfs-lts \
  -append "console=ttyAMA0 ip=dhcp alpine_repo=http://dl-cdn.alpinelinux.org/alpine/edge/main/" \
  -netdev user,id=net0 -netdev user,id=net1 \
  -device virtio-net-device,netdev=net0 -device virtio-net-device,netdev=net1 \
  -nographic

#wget https://dl-cdn.alpinelinux.org/alpine/edge/releases/aarch64/netboot/vmlinuz-lts

#wget https://dl-cdn.alpinelinux.org/alpine/edge/releases/aarch64/netboot/initramfs-lts

  #aarch64
  
  qemu-system-aarch64 \
  -M virt -m 256M -cpu cortex-a57 \
  -kernel vmlinuz-lts -initrd initramfs-lts \
  -append "console=ttyAMA0 ip=dhcp alpine_repo=http://dl-cdn.alpinelinux.org/alpine/edge/main/" \
  -netdev user,id=net0 -netdev user,id=net1 \
  -device virtio-net-device,netdev=net0 -device virtio-net-device,netdev=net1 \
  -nographic
  
