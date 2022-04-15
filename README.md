# technicalshare-front

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

<h1 align="center">
    <img alt="TechnicalShare" title="#TechnicalShare" src="./assets/logo.svg" style="min-width: 420px; margin: 20px 0"/>
</h1>

<h4 align="center"> 
	🍊 TechnicalShare - MVP 🍊
</h4>

<p align="center">
 <a href="#-sobre-o-projeto">Sobre</a> •
 <a href="#-funcionalidades">Funcionalidades</a> •
 <a href="#-layout">Layout</a> • 
 <a href="#-como-executar-o-projeto">Como executar</a> • 
 <a href="#-tecnologias">Tecnologias</a> • 
 <a href="#-equipe">Equipe</a> • 
 <a href="#user-content--licença">Licença</a>
</p>

## 💻 Sobre o projeto

🍊 **TechnicalShare** - é uma plataforma que fornece a possibilidade da empresa cliente registrar e catalogar seus funcionários por áreas de conhecimento e ferramentas mais utilizadas, dando-lhes a possibilidade de se elegerem como "mentores", disponibilizando-se ao contato de outros funcionários que os busquem para tirar dúvidas e fazer networking.

Projeto desenvolvido pelo **Squad 33** durante o Hackaton do **Programa de Formação - Season 3** oferecido pela [FCamara](https://digital.fcamara.com.br/programadeformacao#).

---

## ⚙️ Funcionalidades

- [x] A empresa cliente poderá disponibilizar a plataforma para o cadastro de seus funcionários, fornecendo a possibildade destes cadastrarem:

  - [x] área de conhecimento principal;
  - [x] nível de senioridade dentro da empresa;
  - [x] disponibilidade para dar mentorias;
  - [x] principais links de contato (Linkedin, Whatsapp e Microsoft Teams);
  - [] foto de perfil;

- [x] Uma vez cadastrados na plataforma, os usuários (funcionários da empresa cliente) poderão acessar a plataforma para:
  - [x] ver uma lista completa de usuários (companheiros de trabalho), com suas informações públicas cadastrais;
  - [x] filtrar a visualização da lista de usuários por área de conhecimento;
  - [x] acessar, através da lista de usuários, a página de perfil interna de cada usuário, para entrar em contato através de um de seus links cadastrados ou por email (se o usuário for um mentor);

---

## 🎨 Layout

O layout da aplicação está disponível no Figma:

<a href="https://www.figma.com/file/1SxgOMojOB2zYT0Mdk28lB/Ecoleta?node-id=136%3A546">
  <img alt="Made by tgmarinho" src="https://img.shields.io/badge/Acessar%20Layout%20-Figma-%2304D361">
</a>
<br>
---

## 🚀 Como executar o projeto

Este projeto é divido em duas partes:

1. Backend (<a href="https://github.com/squad33-hackaton/technicalshare-api">Link do Github</a>)
2. Frontend

💡**O Frontend precisa que o Backend esteja sendo executado para funcionar. Acesse o link acima (Link do Github do Backend), siga as instruções para fazer o servidor rodar em sua máquina. Depois retorne às instruções abaixo.**

### Pré-requisitos

Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas:
[Git](https://git-scm.com), [Node.js](https://nodejs.org/en/).
Além disto é bom ter um editor para trabalhar com o código como [VSCode](https://code.visualstudio.com/)

#### 🧭 Rodando a aplicação web (Frontend)

```bash

# Clone este repositório
$ git clone https://github.com/squad33-hackaton/technicalshare-front.git

# Acesse a pasta do projeto no seu terminal/cmd
$ cd technicalshare-front

# Instale as dependências
$ npm install

# Execute a aplicação em modo de desenvolvimento
$ npm run dev

# A aplicação será aberta na porta:3009 - acesse http://localhost:3009

```

---

## 🛠 Tecnologias

As seguintes ferramentas foram usadas na construção do projeto:

#### **Website** ([NuxtJS](https://nuxtjs.org/)) _O projeto foi criado à partir do comando 'create-nuxt-app', uma CLI de para o NuxtJS que já integra alguns pacotes e funcionalidades no mesmo. Abaixo, as tecnologias marcadas com asterisco são as que foram adicionadas ao projeto desta maneira._

- **[Axios](https://github.com/axios/axios)** \*
- **[Vue Router](https://router.vuejs.org/)** \*

> Veja o arquivo [package.json](https://github.com/squad33-hackaton/technicalshare-front/blob/main/package.json)

#### **Utilitários**

- Layout: **[Bootstrap](https://github.com/axios/axios)** \*, **[sweetalert2](https://sweetalert2.github.io/)**, **[element-ui](https://element.eleme.io/#/en-US)**
- Editor: **[Visual Studio Code](https://code.visualstudio.com/)**
- Protótipo: **[Figma](https://www.figma.com/)** → **[Protótipo (TechnicalShare)](https://www.figma.com/file/1SxgOMojOB2zYT0Mdk28lB/Ecoleta)**
- Teste de API: **[Postman](https://www.postman.com/)**
- Ícones: **[Font Awesome](https://fontawesome.com/)**
- Fontes: **[Manrope](https://fonts.google.com/specimen/Manrope)**

---

## 👨‍💻 Equipe

🧡 O Squad 33 é responsável pelo sucesso na entrega desse projeto. 👏

<!--
<table>
  <tr>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars2.githubusercontent.com/u/2254731?s=400&u=0ba16a79456c2f250e7579cb388fa18c5c2d7d65&v=4" width="100px;" alt=""/><br /><sub><b>Diego Fernandes</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">👨‍🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars1.githubusercontent.com/u/4669899?s=460&u=806503605676192b5d0c363e4490e13d8127ed64&v=4" width="100px;" alt=""/><br /><sub><b>Cleiton Souza</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">👨‍🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars2.githubusercontent.com/u/861751?s=460&v=4" width="100px;" alt=""/><br /><sub><b>Robson Marques</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">👨‍🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars3.githubusercontent.com/u/16831337?s=460&v=4" width="100px;" alt=""/><br /><sub><b>Claudio Orlandi</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars2.githubusercontent.com/u/37725197?s=460&u=446439436524c37f66e41f35b607dbb70358d5e4&v=4" width="100px;" alt=""/><br /><sub><b>Vinícios Fraga</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars3.githubusercontent.com/u/26551306?s=460&u=18446655ccae6c2a29eb177a104ecf32f029aa3a&v=4" width="100px;" alt=""/><br /><sub><b>Hugo Duarte</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a>  <a href="https://blog.rocketseat.com.br/" title="Blog">🌐</a></td>

  </tr>
  <tr>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars0.githubusercontent.com/u/39345247?s=460&u=cdff2624a327a43e2765112a54e966a06eac6d79&v=4" width="100px;" alt=""/><br /><sub><b>Joseph Oliveira</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars0.githubusercontent.com/u/10366880?s=460&u=59e93e1752e9d2ece4b7d8e129d60caba9c94207&v=4" width="100px;" alt=""/><br /><sub><b>Guilherme Rodz</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars2.githubusercontent.com/u/6643122?s=460&u=1e9e1f04b76fb5374e6a041f5e41dce83f3b5d92&v=4" width="100px;" alt=""/><br /><sub><b>Mayk Brito</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars2.githubusercontent.com/u/7268910?s=460&u=0b5d9df4232e70fa66ea9f130fad4260378323de&v=4" width="100px;" alt=""/><br /><sub><b>João Paulo</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>
    <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars2.githubusercontent.com/u/14251143?s=460&u=340ed1d854bbacc22b9a3210a18a1f589a28bc40&v=4" width="100px;" alt=""/><br /><sub><b>Luke Morales</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>
     <td align="center"><a href="https://rocketseat.com.br"><img style="border-radius: 50%;" src="https://avatars0.githubusercontent.com/u/5151405?s=460&u=1dbcf0e89087c2dc902d3331b90e532db1543d2b&v=4" width="100px;" alt=""/><br /><sub><b>Luiz Batanero</b></sub></a><br /><a href="https://rocketseat.com.br/" title="Rocketseat">🚀</a></td>

  </tr>
</table> -->

## 📝 Licença

Este projeto esta sobe a licença [MIT](./LICENSE).

---
