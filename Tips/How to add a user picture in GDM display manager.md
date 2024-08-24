O arquivo que determina a imagem de perfil de um usuário no GDM fica localizado em "/var/lib/AccountsService/users/[USER_NAME]"

Este é um arquivo do tipo .desktop (embora não possua esta extensão em seu nome) que, dentre outras coisas, define uma variável "icon" que indica a foto de perfil a ser usada pelo GDM. Este é um exemplo do conteúdo do arquivo:

```
[User]
Language=en_GB
XSession=ubuntu
Icon=/var/lib/AccountsService/icons/dad
```

**Em teoria**, por padrão, o GDM procura pelo arquivo ~/.face, que deve ser uma imagem PNG ou JPEG. Se tal imagem não for encontrada, o GDM usará uma imagem de rosto genérica. 

**Na prática**, o que funcionou para mim foi colocar a imagem que desejo usar como foto de usuário em "/var/lib/AccountsService/icons/", nomeando-a com o nome do meu usuário sem extensão (i.e., apenas o nome, sem o .png ou .jpg no final) e adicionar o caminho para esta imagem na variável Icon do arquivo em "/var/lib/AccountsService/users/[USER_NAME]".
