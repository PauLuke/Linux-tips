1. Certifique-se de que seu sistema tem instalado o git e os pacotes da linguagem Go

```
sudo pacman -S git go
```

2. Crie uma pasta para o git no seu usuário

```
mkdir git
```

3. Entre na pasta do git e use o comando abaixo para baixar o código fonte do YAY

```
cd git/

git clone https://aur.archlinux.org/yay.git
```

4. Em seguida, acesse a pasta criada;

```
cd yay
```

5. Finalmente, use o comando abaixo para compilar e instalar o programa;

```
makepkg -si
```
