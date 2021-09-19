# Comandos para Git e Github

### Primeiro passo: configurar o git
- git config --local user.name "Seu nome aqui"
- git config --local user.email "seu@email.aqui"


## Conceitos de Git
- HEAD: Estado atual do nosso código, ou seja, onde o Git os colocou
- Working tree: Local onde os arquivos realmente estão sendo armazenados e editados
- index: Local onde o Git armazena o que será commitado, ou seja, o local entre a working tree e o repositório Git em si.

or create a new repository on the command line
echo "# C_Language_Study" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/lpfnascimento/C_Language_Study.git
git push -u origin main

or push an existing repository from the command line
git remote add origin https://github.com/lpfnascimento/C_Language_Study.git
git branch -M main
git push -u origin main
