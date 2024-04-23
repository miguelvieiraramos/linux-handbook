# GRUB 2

O grub é um um boot manager que permite escolher qual sistema operacional o usuário deseja utilizar.

O arquivo de configuração é o /boot/grub/grub.cfg, mas esse arquivo não deve ser alterado manualmente. Para realizar alterações é necessário alterar o arquivo /etc/default/grub ou algum dos arquivos do diretório /etc/grub.d/. As alterações realizadas só terão efeito quando o usuário rodar o comando update-grub (debian ou ubuntu) e ele reescrever o /boot/grub/grub.cfg com as novas configurações.

Links úteis:

- https://help.ubuntu.com/community/Grub2
- https://access.redhat.com/documentation/pt-br/red_hat_enterprise_linux/7/html/system_administrators_guide/ch-working_with_the_grub_2_boot_loader
