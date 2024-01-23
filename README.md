# To-Do List React Js
Desenvolvido por **João Paulo Souza Silva**, **Wagner Santos Duarte** e **Ednei Soares de Carvalho Filho**

---

## Descrição do objetivo
O objetivo deste projeto é empregar o React Js como plataforma para o desenvolvimento de um projeto compacto, neste caso, uma lista de tarefas (To-Do List). O propósito é demonstrar a aplicação prática desta tecnologia, fornecendo aos estudantes uma base de conhecimento sobre o React Js. Através deste projeto, os estudantes poderão entender melhor como o código é estruturado e implementado usando o React Js.

---

## Descrição para instalação dos softwares necessários

Inicialmente devemos criar um projeto com react js, seguindo os seguintes passos:

Deve Se instalar um editor de codigo, como por exemplo o Visual Studio Code utilizado para o desenvolvimento do mini projeto. Você pode baixar o Vs Code em [Clique Aqui](https://code.visualstudio.com/)

Para a utilização do To Do List é necessário ter um navegador web, como por exemplo o Google Chrome

instalar o Node.js e npm: Certifique-se de ter o Node.js instalado em seu sistema, pois o npm (Node Package Manager) vem junto com ele. Você pode baixar o Node.js em [Clique Aqui](https://nodejs.org/.)

Instalar o Create React App: O Create React App é uma ferramenta que facilita a configuração inicial do seu projeto React. Para instalá-lo, abra seu terminal e execute o seguinte comando:

  ```bash
    npx create-react-app todolist
  ```

---

## Passo-a-Passo para o desenvolvimento
Abra o arquivo src/App.js. Você verá uma estrutura parecida com essa: 

![Codigo Base](/src/images/code/image_00.png)

Após abrir apague, as informações já existentes e deixe o arquivo com a seguinte estrutura: 

![Estado Inicial](/src/images/code/image_01.png)

Durante a elaboração da To Do List, apresentamos três funcionalidades essenciais: inclusão, exclusão e edição de tarefas. No entanto, antes de implementar essas funções, é necessário criar os estados usando o useState, também denominado "hook de estado", e realizar algumas importações.

![Importações e useState](/src/images/code/import_useetate.png)

import React, { useState } from 'react';: Importa a biblioteca React e o hook useState do React. O useState é usado para gerenciar o estado da aplicação.

import './App.css';: Importa um arquivo de estilos CSS para a aplicação.

function App() : Início da definição da função principal App.

