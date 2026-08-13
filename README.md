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

## Passo 2 — Baixar o projeto

Você vai receber o projeto do professor de uma destas formas:

- **Como arquivo .zip:** baixe o arquivo, clique com o botão direito nele e
  escolha **Extrair tudo...**. Guarde a pasta extraída em um lugar fácil de
  achar, por exemplo `Documentos`.
- **Pelo GitHub (se o professor passar um link):** clique no botão verde
  **Code** e depois em **Download ZIP**, e extraia como acima.

Ao final, você terá uma pasta chamada `filmeApp` (ou parecido) com os arquivos
do projeto dentro.

---

## Passo 3 — Abrir a pasta no terminal

Você precisa "entrar" na pasta do projeto pelo terminal.

**Jeito mais fácil (recomendado):** instale o **VS Code**
(<https://code.visualstudio.com>), abra o programa, vá em
**File > Open Folder / Arquivo > Abrir Pasta** e escolha a pasta do projeto.
Depois abra o terminal em **Terminal > New Terminal / Novo Terminal**. Ele já
vai estar na pasta certa.

**Sem o VS Code:** abra a pasta do projeto no Explorer, clique na barra de
endereço no topo, digite `powershell` e aperte Enter. O PowerShell abre já
dentro da pasta.

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
