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

![Codigo Base](/images/code/image_00.png)

Após abrir apague, as informações já existentes e deixe o arquivo com a seguinte estrutura: 

![Estado Inicial](/images/code/image_01.png)

Durante a elaboração da To Do List, apresentamos três funcionalidades essenciais: inclusão, exclusão e edição de tarefas. No entanto, antes de implementar essas funções, é necessário criar os estados usando o useState, também denominado "hook de estado", e realizar algumas importações.

![Importações e useState](/images/code/import_useetate.png)

**import React, { useState } from 'react';**: Importa a biblioteca React e o hook useState do React. O useState é usado para gerenciar o estado da aplicação.

**import './App.css';**: Importa um arquivo de estilos CSS para a aplicação.

**function App()**: Início da definição da função principal App.

Todos os useState seguem o mesmo formato, mudando apenas seu valor inicial. Por exemplo na linha **const [newTask, setNewTask] = useState('');**

 - **const**: Declaração de uma constante, indicando que **newTask** será uma variável constante que não pode ser reatribuída.

 - **[newTask, setNewTask]**: Utiliza a desestruturação de array para atribuir dois valores a partir do retorno de **useState**.
 
    - **newTask**: Representa o estado atual da variável, que armazenará o conteúdo da nova tarefa.

    - **setNewTask**: É uma função que permite modificar o estado **newTask**.

 - **= useState('');**: Inicializa o estado **newTask** com um valor inicial vazio, neste caso, uma string vazia **(' ')**. O valor inicial especificado aqui é utilizado quando o componente é montado pela primeira vez.

A função de adição de tarefa segue a seguinte estrutura:

![Funçã0 de adicionar tarefa](/images/code/add_task.png)

**if (newTask.trim() !== '')**: Este bloco condicional verifica se a string **newTask** (presumivelmente uma nova tarefa a ser adicionada) não está vazia após a remoção de espaços em branco no início e no final usando **trim()**.

**if (editMode)**: Este bloco condicional verifica se o modo de edição **(editMode)** está ativado. Se estiver, isso significa que o usuário está editando uma tarefa existente em vez de adicionar uma nova.

**const updatedTasks = [...tasks];**: Cria uma cópia do array tasks usando o operador spread (**[...]**). Isso é feito para evitar a mutação direta do estado, seguindo as práticas recomendadas de imutabilidade em React.

**updatedTasks[editIndex] = newTask;**: Atualiza a tarefa na posição editIndex da cópia **updatedTasks** com a nova tarefa (**newTask**) que está sendo editada.

**setTasks(updatedTasks);**: Atualiza o estado das tarefas com a nova cópia atualizada que inclui a edição.

**setEditMode(false); e setEditIndex(null);**: Desativa o modo de edição e redefine o índice de edição para null, indicando que não há mais edição em andamento.

**setShowModal(false);**: Esconde modal ou janela de edição que estava aberta.

**setTasks([...tasks, newTask]);**: Se não estiver no modo de edição, isso adiciona a nova tarefa ao final do array de tarefas usando novamente o operador spread para criar uma nova cópia do array.

**setNewTask('');**: Limpa o conteúdo da variável de estado **newTask**, preparando-a para uma nova entrada.

**else { setShowAlert(true); }**: Se a string **newTask** estiver vazia, exibe um alerta. 

A função de edição de tarefa segue a seguinte estrutura:

![Função de editar tarefa](/images/code/edit_task.png)

**const editTask = (index)**: Declaração de uma constante chamada **editTask**, que é uma função arrow (função de seta) que aceita um parâmetro chamado index.

**setNewTask(tasks[index]);**: Essa linha usa a função **setNewTask** para atualizar o estado **newTask** com o valor da tarefa localizada no índice fornecido no array **tasks**. 

**setEditMode(true);**: Aqui, a função **setEditMode** é usada para definir o estado editMode como **true**. Possibilitando a edição de uma tarefa.

**setEditIndex(index);**: A função **setEditIndex** é usada para atualizar o estado **editIndex** com o valor do índice fornecido como parâmetro.

**setShowModal(true);**: Utilizando a função **setShowModal**, o estado **showModal** é definido como **true**. Isso torna o modal de edição visível.

A função de deleção de tarefa segue a seguinte estrutura:

![Função de excluir tarefa](/images/code/delet_task.png)

**const deleteTask = (index)**: Aqui, está sendo declarada uma função chamada **deleteTask** que recebe um parâmetro chamado **index**. Essa função é responsável por excluir uma tarefa.

**const updatedTasks = [...tasks];**: Esta linha cria uma cópia da lista de tarefas original. O operador spread (**...**) é usado para criar uma cópia rasa do array **tasks**. Isso é feito para evitar a mutação direta do estado original.

**updatedTasks.splice(index, 1);**: Aqui, a função **splice** é utilizada para remover um elemento do array **updatedTasks**. O parâmetro **index** indica a posição do elemento a ser removido, e o **1** indica quantos elementos devem ser removidos a partir dessa posição.

**setTasks(updatedTasks);**: Finalmente, a função **setTasks** é chamada com a cópia atualizada do array de tarefas. Isso atualiza o estado da aplicação para refletir a remoção da tarefa.

Agora dentro do bloco do ‘**return**’ inserimos os seguintes códigos para fazer a chamada das funções e mostrar na tela as tarefas. 

![Primeira parte do bloco return](/images/code/return_01.png)

'<div className="background-image"></div>':Define uma div para colocar uma imagem ao fundo da tela. Para que a imagem apareça, crie dentro da pasta src uma pasta chamada images e dentro desta pasta coloque a logo do React js de preferência sem fundo.


