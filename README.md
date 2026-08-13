# Cineteca

Projeto da **primeira aula de React**. Uma pequena coleção de filmes que
demonstra três conceitos fundamentais: **componentes**, **props** e **estado**.

Este guia foi feito para quem está começando e usa **Windows**. Siga os passos
na ordem.

---

## Passo 1 — Instalar o Node.js (só na primeira vez)

O React precisa do **Node.js** para funcionar. Ele vem junto com o `npm`, o
programa que instala as dependências e roda o projeto.

1. Acesse o site oficial: <https://nodejs.org>
2. Baixe a versão marcada como **LTS** (a recomendada, mais estável).
3. Abra o arquivo baixado (`.msi`) e clique em **Next / Avançar** até o fim,
   sem mudar nada. No final, clique em **Install / Instalar**.
4. Para conferir se deu certo, abra o **Prompt de Comando** ou o **PowerShell**
   (aperte a tecla Windows, digite `powershell` e abra) e digite:

   ```bash
   node -v
   ```

   ```bash
   npm -v
   ```

   Se aparecer um número de versão em cada um (por exemplo `v20.11.0`), a
   instalação funcionou.

---

## Passo 2 — Instalar o Git (só na primeira vez)

Vamos baixar o projeto usando o **Git**. No Windows, instale assim:

1. Acesse <https://git-scm.com/download/win> (o download começa sozinho).
2. Abra o arquivo baixado e clique em **Next / Avançar** até o fim, sem mudar
   nada, e depois em **Install / Instalar**.
3. Para conferir, abra o **PowerShell** (tecla Windows, digite `powershell`) e
   digite:

   ```bash
   git --version
   ```

   Se aparecer um número de versão, deu certo.

---

## Passo 3 — Clonar (baixar) o projeto

"Clonar" é baixar uma cópia do projeto que está no GitHub para o seu computador.

1. Abra o **PowerShell** e vá até a pasta onde você quer guardar o projeto,
   por exemplo a pasta Documentos:

   ```bash
   cd Documentos
   ```

2. Clone o repositório:

   ```bash
   git clone https://github.com/JefersonQueiroga/filmeApp.git
   ```

3. Entre na pasta que acabou de ser criada:

   ```bash
   cd filmeApp
   ```

Pronto: agora o terminal está dentro da pasta do projeto.

> Dica: para abrir esse projeto no editor, instale o **VS Code**
> (<https://code.visualstudio.com>). Com o terminal já dentro da pasta
> `filmeApp`, digite `code .` para abrir o projeto inteiro nele. Dentro do
> VS Code você também pode abrir um terminal em
> **Terminal > New Terminal / Novo Terminal**, que já vem na pasta certa.

---

## Passo 4 — Instalar as dependências (só na primeira vez)

Com o terminal aberto na pasta do projeto, digite:

```bash
npm install
```

Isso baixa tudo que o projeto precisa (a pasta `node_modules` será criada).
Pode demorar um pouco na primeira vez. É normal.

---

## Passo 5 — Rodar o projeto

Ainda no terminal, digite:

```bash
npm run dev
```

Vai aparecer um endereço, geralmente <http://localhost:5173>. Segure a tecla
**Ctrl** e clique no link, ou copie e cole no navegador. A aplicação abre.

Para **parar** o projeto, volte ao terminal e aperte **Ctrl + C**.

> Dica: enquanto o projeto está rodando, se você editar um arquivo e salvar,
> a página se atualiza sozinha no navegador.

---

## Conceitos mostrados

### Componente

Um componente é um pedaço reutilizável da tela, escrito como uma função que
retorna o que deve aparecer (JSX). Quebrar a tela em componentes pequenos
deixa o código mais fácil de ler e reaproveitar.

### Props

Props são as informações que um componente recebe "de fora", como os parâmetros
de uma função. Dentro do `.map()`, cada filme é passado para um `CartaoFilme`
(`filme={...}`). Props seguem sempre de cima para baixo: do componente pai para
o filho.

### Estado (useState)

Estado é a "memória" de um componente — um valor que pode mudar com a interação
do usuário e faz a tela se redesenhar sozinha. Cada `CartaoFilme` guarda em
estado se o filme foi assistido; ao clicar no botão, `setAssistido` troca esse
valor e o React atualiza o cartão na hora. A navegação entre as telas "Filmes"
e "Sobre" também usa `useState`.

---

## Estrutura dos arquivos

```
src/
├── data/
│   └── filmes.js           # os dados (separados da interface)
├── components/
│   ├── CartaoFilme.jsx     # mostra 1 filme + botão com useState
│   ├── PaginaFilmes.jsx    # a tela com a lista de filmes
│   └── PaginaSobre.jsx     # a tela "Sobre"
├── App.jsx                 # componente principal (menu + navegação)
├── App.css                 # estilos
├── index.css               # estilo global básico
└── main.jsx                # ponto de partida da aplicação
```
