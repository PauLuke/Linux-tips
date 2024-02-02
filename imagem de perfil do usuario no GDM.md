O arquivo que determina a imagem de perfil no GDM fica localizado no seguinte diretório:

/var/lib/AccountsService/users/[USER_NAME]

Este é um arquivo do tipo .desktop (embora não possua esta extensão na prática) que, dentre outras coisas, guarda uma variável "icon" que indica a foto de perfil usada pelo GDM. Por padrão uma imagem png ou jpg denominada ~/.face é indicada, mas isso pode ser alterado. Uma alternaiva é adicionar uma imagem (96x96 ?) em "/var/lib/AccountsService/icons/" com o nome do seu usuário e sem extensão (i.e., apenas o nome sem o .png ou .jpg).
