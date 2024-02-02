Em resumo o comando é:

```
sudo apt install qemu virt-manager dnsmasq
```

Você pode verificar se libvirtd foi iniciado digitando:

```bash
sudo systemctl is-active libvirtd
```

 A saída deve ser: `active` , se por algum motivo não estiver ativa, então faça manualmente com o comando:

```
sudo systemctl enable --now libvirtd
```

Para você conseguir criar “máquinas virtuais”, certifique-se de incluir seu usuário aos grupos: `kvm` e `libvirt` da seguinte forma:

```bash
sudo usermod -aG libvirt $USER
sudo usermod -aG kvm $USER
```