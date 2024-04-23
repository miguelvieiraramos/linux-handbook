# Root e Access Control

## su
su é a sigla para substitute user. Basicamente esse programa permite um usuário logar como outro usuário e rodar comandos, mas antes pede um login e senha.

## sudo

O sudo é parecido, porém você está simplesmente rodando um comando como um usuário diferente do seu e não está definitivamente logado como ele. A vantagem do sudo é que ele mantém bons logs dos comandos utilizados e quem os executou, por exemplo, se eu na conta miguel executar um comando como root usando o sudo, essa informação estará logada e o administrador vai saber que foi o miguel. Já o `su` não tem essa rastreabilidade.

## Arquivos

Os arquivos possuem um owner e um group. O dono pode definir os grupos que têm acesso ao seu arquivo e o que eles podem fazer com o arquivo, por exemplo somente ler.
