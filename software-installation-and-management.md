# Software installation and management

O dpkg é o gerenciador de pacotes do Debian que também é usado pelo Ubuntu. Você pode usar o dpkg para instalar pacotes `.deb` manualmente, porém atualmente o comando `apt` oferece uma interface de alto nível que resolve a maior parte dos casos. Então, basicamente o apt usando o dpkg por baixo dos panos para gerenciar e instalar os pacotes.

O apt possui um arquivo /etc/apt/source.list que contém os repositórios remotos que de lá podemos baixar os pacotes para que o apt instale na nossa máquina. É possível alterar essa lista.

Segue alguns links úteis para como mexer no apt:

- https://help.ubuntu.com/community/AptGet/Howto
- https://help.ubuntu.com/community/Repositories/CommandLine
