# 🛒 Lista de Compras

Aplicação mobile desenvolvida com **React Native, Expo e TypeScript** para gerenciamento simples de uma lista de compras.

O projeto foi desenvolvido como atividade prática de desenvolvimento de aplicações, seguindo uma estrutura baseada em componentes reutilizáveis, tipagem com TypeScript e gerenciamento de estado com React Hooks.

---

## 📌 Sobre o Projeto

O **Lista de Compras** permite ao usuário cadastrar produtos informando seu nome e quantidade, visualizar os itens adicionados e removê-los da lista.

A aplicação possui uma interface simples e responsiva, com componentes separados para facilitar a organização, manutenção e evolução do código.

O projeto utiliza **Expo** como ambiente de desenvolvimento e **React Native** para construção da interface, com **TypeScript** para garantir maior segurança e organização no código.

---

## 🎯 Objetivos

* Desenvolver uma aplicação utilizando React Native.
* Utilizar Expo para execução e testes do projeto.
* Aplicar TypeScript na tipagem dos dados.
* Trabalhar com componentes reutilizáveis.
* Utilizar `useState` para gerenciamento de estado.
* Implementar cadastro e remoção de itens.
* Aplicar validações nos dados inseridos pelo usuário.
* Organizar o projeto seguindo uma estrutura de componentes.

---

## ⚙️ Funcionalidades

### ➕ Adicionar produtos

O usuário pode informar:

* Nome do produto;
* Quantidade desejada.

Após clicar em **"Adicionar item"**, o produto é inserido na lista. Caso a quantidade não seja informada, o sistema utiliza **1 como quantidade padrão**.

### 🗑️ Remover produtos

Cada produto possui um botão de remoção. Ao pressioná-lo, o item correspondente é retirado da lista utilizando seu identificador único.

### ✅ Validação

O sistema impede o cadastro de produtos sem nome e apresenta um alerta ao usuário:

> "Atenção — Digite o nome do produto."

Essa validação evita que itens sem identificação sejam adicionados à lista.

### 📋 Lista de produtos

Os produtos são apresentados utilizando o componente `FlatList`, com identificação individual por meio do `id` de cada item.

### 🧺 Lista vazia

Quando não existem produtos cadastrados, a aplicação apresenta uma mensagem informando que a lista está vazia e orienta o usuário a adicionar um produto.

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia         | Utilização                              |
| ------------------ | --------------------------------------- |
| **React Native**   | Desenvolvimento da interface mobile     |
| **Expo**           | Ambiente de desenvolvimento e execução  |
| **TypeScript**     | Tipagem e segurança do código           |
| **React Hooks**    | Gerenciamento de estado                 |
| **FlatList**       | Renderização da lista de produtos       |
| **JavaScript/JSX** | Lógica e estrutura dos componentes      |
| **Babel**          | Transformação e configuração do projeto |

As versões e dependências principais estão definidas no `package.json`, incluindo Expo, React, React Native, React Native Web e TypeScript.

---

## 📂 Estrutura do Projeto

```text
lista-de-compras/
│
├── package.json
├── app.json
├── babel.config.js
├── tsconfig.json
├── types.ts
├── index.tsx
├── App.tsx
│
└── components/
    ├── Cabecalho.tsx
    ├── FormularioItem.tsx
    ├── ItemCompra.tsx
    └── ListaCompras.tsx
```

A estrutura segue a organização definida no roteiro da atividade.

---

## 🧩 Organização dos Componentes

### `App.tsx`

É o componente principal da aplicação.

Responsabilidades:

* Controlar o estado dos produtos;
* Adicionar novos itens;
* Remover itens;
* Integrar os demais componentes;
* Exibir o contador de itens.

O estado principal utiliza:

```tsx
useState<ItemDeCompra[]>([])
```

e as funções `adicionarItem()` e `removerItem()` controlam as alterações na lista.

### `types.ts`

Define a interface `ItemDeCompra`, responsável pela estrutura dos produtos:

```ts
interface ItemDeCompra {
  id: string;
  nome: string;
  quantidade: number;
}
```

Essa tipagem permite que os componentes trabalhem com uma estrutura padronizada.

### `Cabecalho.tsx`

Responsável pela apresentação do cabeçalho da aplicação, contendo:

* Ícone de carrinho;
* Título **"Minha Lista de Compras"**;
* Subtítulo explicativo.

### `FormularioItem.tsx`

Responsável pela entrada de dados do usuário.

Possui:

* Campo para nome do produto;
* Campo para quantidade;
* Botão para adicionar;
* Validação do nome;
* Controle dos campos com `useState`.

### `ItemCompra.tsx`

Representa individualmente cada produto da lista.

Exibe:

* Nome;
* Quantidade;
* Botão para remoção.

### `ListaCompras.tsx`

Responsável pela apresentação de todos os produtos cadastrados utilizando `FlatList`.

Também controla a apresentação da mensagem de lista vazia.

---

## 🚀 Como Executar o Projeto

### 1. Pré-requisitos

É necessário possuir instalado:

* **Node.js**
* **npm**
* **Expo**
* **Expo Go** para testes em dispositivo físico, caso desejado.

### 2. Instalação

Clone o repositório:

```bash
git clone URL_DO_SEU_REPOSITORIO
```

Entre na pasta:

```bash
cd lista-de-compras
```

Instale as dependências:

```bash
npm install
```

Caso necessário, instale o `expo-status-bar`:

```bash
npm install expo-status-bar
```

Essa instalação também está prevista no roteiro da atividade.

### 3. Iniciar o projeto

Execute:

```bash
npm start
```

Após iniciar o Expo, é possível executar a aplicação em:

* **Android:** pressione `a`;
* **iOS:** pressione `i` no macOS;
* **Web:** pressione `w`;
* **Celular:** escaneie o QR Code utilizando o Expo Go.

---

## 🔍 Verificação do TypeScript

O projeto possui um comando específico para verificar possíveis erros de tipagem:

```bash
npm run typecheck
```

Também é possível utilizar:

```bash
npx tsc --noEmit
```

O resultado esperado é a execução sem mensagens de erro.

---

## 🧪 Testes Realizados

A aplicação deve ser validada através dos seguintes cenários:

### Adicionar item

```text
Produto: Pão
Quantidade: 5
Resultado: Pão — Qtd: 5
```

### Nome vazio

```text
Nome: vazio
Quantidade: 2
Resultado: alerta de validação
```

Nenhum produto deve ser adicionado.

### Quantidade não informada

```text
Produto: Ovos
Quantidade: vazio
Resultado: Ovos — Qtd: 1
```

A quantidade padrão utilizada é `1`.

### Remover item

Ao pressionar o botão `✕`, o produto correspondente deve desaparecer da lista e o contador deve ser atualizado.

### Lista vazia

Após remover todos os produtos, deve aparecer:

```text
🧺
Sua lista está vazia
Adicione um produto no campo acima
```

O contador deve apresentar `0 itens na lista`.

---

## 🔄 Fluxo da Aplicação

```text
        ┌─────────────────────┐
        │   Aplicação inicia  │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │ Exibe lista inicial │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │ Informar produto    │
        │ + quantidade        │
        └──────────┬──────────┘
                   │
                   ▼
        ┌─────────────────────┐
        │ Validar informações │
        └───────┬─────┬───────┘
                │     │
          válido│     │inválido
                │     │
                ▼     ▼
       ┌────────────┐ ┌─────────────┐
       │ Adicionar  │ │ Exibir      │
       │ produto    │ │ alerta      │
       └──────┬─────┘ └─────────────┘
              │
              ▼
       ┌──────────────┐
       │ Exibir item  │
       │ na lista     │
       └──────┬───────┘
              │
              ▼
       ┌──────────────┐
       │ Remover item │
       │ quando       │
       │ solicitado   │
       └──────────────┘
```

---

## 📚 Conceitos Aplicados

Durante o desenvolvimento foram utilizados conceitos importantes de desenvolvimento mobile:

* Componentização;
* Props;
* Estado com `useState`;
* Interfaces TypeScript;
* Tipagem de funções;
* `FlatList`;
* `TextInput`;
* `TouchableOpacity`;
* `Alert`;
* `StyleSheet`;
* Renderização condicional;
* Validação de entrada;
* Importação e exportação de componentes.

O roteiro também estabelece como prática a criação do componente, sua importação no `App.tsx`, utilização na JSX e posterior teste com `npm start`.

---

## ✅ Checklist

* [x] `package.json` configurado
* [x] `app.json` configurado
* [x] `babel.config.js` configurado
* [x] `tsconfig.json` configurado
* [x] Interface `ItemDeCompra` criada
* [x] `index.tsx` configurado
* [x] `App.tsx` desenvolvido
* [x] Pasta `components/` criada
* [x] `Cabecalho.tsx` desenvolvido
* [x] `FormularioItem.tsx` desenvolvido
* [x] `ItemCompra.tsx` desenvolvido
* [x] `ListaCompras.tsx` desenvolvido
* [x] Adição de produtos implementada
* [x] Remoção de produtos implementada
* [x] Validação do nome implementada
* [x] Quantidade padrão implementada
* [x] Estado da aplicação implementado
* [x] Lista vazia implementada
* [x] TypeScript validado
* [x] Testes finais realizados

O checklist corresponde às etapas finais estabelecidas no roteiro da atividade.

---

## 🎓 Atividade Acadêmica

Projeto desenvolvido para fins acadêmicos como atividade prática de **Desenvolvimento de Sistemas**, seguindo o roteiro de codificação fornecido para a construção da aplicação **Lista de Compras**.

---

## 👨‍💻 Autor

**Arthur Santos da Silva**

**SENAI A. Jacob Lafer**
Curso de **Desenvolvimento de Sistemas**

---

## 📄 Licença

Este projeto foi desenvolvido para fins **educacionais e acadêmicos**.
