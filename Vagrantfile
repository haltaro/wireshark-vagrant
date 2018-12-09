# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  # 仮想マシン上で動作するWiresharkのGUIを直接使うため，x forwardingする．
  config.ssh.forward_x11 = true

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update

	# x11 forwarding関連．
    apt-get install x11-apps -y

    # WireShark．対話型を回避するために細かい設定が必要．
    DEBIAN_FRONTEND=noninteractive apt-get -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" install wireshark
    # 一般ユーザも使えるよう，dumpcapの設定を変更する．
    setcap 'CAP_NET_RAW+eip CAP_NET_ADMIN+eip' /usr/bin/dumpcap

  SHELL
end
