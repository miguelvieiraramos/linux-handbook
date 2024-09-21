# Filesystem

# mount and unmount

O comando mount adiciona um sistema de arquivos encontrados em dispositivo (hd ssd) à árvore de arquivos do linux. O unmount faz justamente o contrário, pega esse sistema de arquivos e remove da árqvore de arquivos.

# hier

O linux tem diversos diretório que a gente não entende o seu proposito. o comando `man hier` pode nos dar mais informação da função de cada um.

# Tipos de arquivo

O comando `file` nos diz qual é o tipo do arquivo que pode ser: Regular files, Directories, Character device, Block device, Local domain socket, Named Pipes, Symbolic links.

O comando `ls` também identifica o tipo do arquivo logo no começo, por exemplo:
```
drwxrwxr-x 8 miguel miguel  4096 abr 22 21:48 .git
```

A letra "d" no inicio indica que esse arquivo é um diretório.


## Hard Links

Os hard links são criados com o comando `ln` e eles apontam diretamente para o arquivo linkado, portanto eles possuem até o mesmo inode (identificador do arquivo no sistema), se o arquivo original for deletado, o conteúdo do arquivo em sí ainda vai estar no HD/SSD e você continua podendo ver pelo Hard Link.

## Symbolic Links

Criado pelo comando `ln -s'. O Symbolic Link não é um link direto, então possui inode diferente e se o arquivo original for deletado o symbolic link não irá funcionar mais.


# Permissões

Os arquivos e diretórios possuem alguns bits que representam as permissões. O primeiro bit mostra o tipo do arquivo, os próximos nove representam as permissões do owner, group e others (nessa ordem). E a ordem é sempre read-write-execute. Então o arquivo abaixo mostra que o owner pode ler, escrever e executar, o grupo também, porém os outros só podem ler e executar.
```
drwxrwxr-x 8 miguel miguel  4096 abr 22 21:48 .git
```

A gente pode alterar o owner do arquivo pelo comando `chown` e alterar o grupo pelo `chgrp`
