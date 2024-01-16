# Guia de como instalar o WSL para utilização do Pyenv e Poetry em projetos de Desenvolvimento e/ou Dados

---

1.O primeiro passo a ser realizado e fazer a instalação do WSL no seu Windows:
2. Abra o CMD do seu Windows, pode ser utilizado o atalho ` Windows + R ` para abrir a opção de executar e digitar cmd. Com CMD aberto faça

  ```
    wsl --install
    wsl --update
  ```

Após estas etapas você deve reiniciar o computador, após reiniciar o computador o pronpt de instalação do Ubuntu irá abrir automaticamente para definir nome do usuário do WSL(Ubuntu) E senha.
Outra forma de instalar é através da Microsoft Store, procurando a distro do seu interesse.

---

Agora vamos as instalações das dependências para o pyenv e poentry.

Primeiro vamos dar um update no Linux.

` sudo apt-get update `

Após finalização da atualização você vai instalar os pacotes do linux necessários

```
    sudo apt install -y build-essential git libexpat1-dev libssl-dev zlib1g-dev \
    libncurses5-dev libbz2-dev liblzma-dev \
    libsqlite3-dev libffi-dev tcl-dev linux-headers-generic libgdbm-dev \
    libreadline-dev tk tk-dev
```

Após finalização da depedências, você deve clonar o pyenv

```
curl https://pyenv.run | bash 
```

Agora vamos configurar o pyenv para carregar automaticamente no terminal
```
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc****
```

E utilizar o ` exec "$SHELL" ` para reiniciar o Shell, para atualizar as ultimas configurações

---

Agora é propriamente a etapa de configuração do pyenv:
-Você pode utilizar o comando ` pyenv versions ` para verificar todas as versões de python instaladas;
-Você pode utilizar o comando ` pyenv install -l ` para listar todas as versões que estão disponíveis para instalação;
-Você pode utilizar o comando ` pyenv install X.X ` para instalar a versão desejado (X.X seria a versão desejada. Ex: 3.11.7);
-Você pode utilizar o comando ` pyenv global X.X ` para definir a versão desejada como global;
-Você pode utilizar o comando ` pyenv local X.X ` para definir a versão desejada como local;

---

Agora vamos instalar o pyenv:

1. Você deve rodar o comando ` pyenv local X.X `
2. Para iniciar um projeto utilizando o poetry você pode usar o comando ` poetry new projeto `, sendo projeto o nome que você deseja colocar
3. Você pode acessar a pasta do seu projeto ` cd projeto `, para após rodar o comando ` code . ` assim você vai instalar um pacote que fara a conexão do *Visual Studio Code* com seu WSL, para isso você deve ter o *Visual Studio Code* instalado no seu Windows, como também a extenção *WSL*.
4. Posteriormente você pode utilizar o comando ` poetry config virtualenvs.in-project true `, você está dizendo para o poetry que a pasta do ambiente virtual ficará dentro da pasta do projeto.
5. Finalmente você pode utilizar o ` poetry shell ` para iniciar o ambiente virtual.
6. Com isso você está pronto para começar o seu projeto.

---

## Espero que tenha ajudado

Para construir esse passo-a-passo segui os seguintes sites:
- https://github.com/pyenv/pyenv
- https://python-poetry.org/

Fiz também um vídeo mostrando o lado prático deste passo-a-passo:
https://www.youtube.com/watch?v=qCD3MBE6xoo
