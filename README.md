from pathlib import Path

# Conteúdo do README extraído do documento
readme_content = """
# Know Your Fan - FURIA

Este documento descreve o funcionamento da página "Know Your Fan - FURIA", explicando passo a passo seus elementos visuais e lógicos.

---

## 1. Estrutura Geral

A página é uma interface de cadastro de fãs da organização FURIA, com estilização neon e suporte a modo escuro e claro. Os dados do fã são armazenados temporariamente na sessão e exibidos em uma seção personalizada após o cadastro.

---

## 2. Elementos Visuais (HTML + CSS)

### 2.1 Header

- Exibe o título "Know Your Fan - FURIA".
- Tem fundo escuro com borda verde neon e uma animação de aparição.

### 2.2 Botão de Alternância de Tema

- Posicionado no canto superior esquerdo.
- Alterna entre modo escuro (`dark-mode`) e claro (`light-mode`) usando a função `toggleTheme()`.

### 2.3 Formulário de Cadastro

Contém os seguintes campos:

- Nome
- Idade
- Rede Social (Twitter, Instagram, Discord)
- Nome de usuário (deve iniciar com @)
- Jogo favorito
- Influenciador favorito
- O que mais gosta na FURIA (textarea)
- O que poderia melhorar na FURIA (textarea)
- Botão "Cadastrar"

### 2.4 Seção de Perfil

- Área onde os dados cadastrados são exibidos após o envio, incluindo:
  - Dados pessoais e preferências
  - Interações simuladas
  - Ranking calculado
  - Hashtags e badges visuais
  - Link para a rede social da FURIA correspondente

---

## 3. Lógica em JavaScript

### 3.1 Cadastro de Fã (`cadastrarFan()`)

- Captura os dados dos campos preenchidos.
- Valida:
  - Preenchimento de todos os campos obrigatórios.
  - Que o nome de usuário comece com "@".
- Gera um valor aleatório de interações entre 0 e 99.
- Determina o ranking usando `obterRanking()`.
- Cria um objeto com os dados e salva no `sessionStorage`.
- Exibe a seção de agradecimento personalizada via `mostrarAgradecimento()`.
- Limpa os campos do formulário com `limparCampos()`.

### 3.2 Exibir Perfil e Agradecimento (`mostrarAgradecimento()`)

- Exibe uma mensagem de agradecimento.
- Mostra os dados do perfil do fã em um formato visual.
- Inclui um botão com link dinâmico para a rede social da FURIA baseada na seleção do fã.

### 3.3 Função de Ranking (`obterRanking()`)

- Classifica os fãs de acordo com o número de interações:
  - Bronze < 30
  - Prata >= 30
  - Ouro >= 40
  - Platina >= 50
  - Diamante >= 60
  - Grão Mestre >= 70
  - Mestre >= 80
  - Challenger >= 90

### 3.4 Alternância de Tema (`toggleTheme()`)

- Alterna classes no `body` para mudar o tema da interface.

### 3.5 Limpeza dos Campos (`limparCampos()`)

- Restaura os valores dos campos do formulário para os padrões.

### 3.6 Limpeza de Dados na Recarregação

- `window.onload` limpa os dados da sessão a cada carregamento de página.

---

## 4. Considerações Finais

Esta página oferece uma experiência interativa e gamificada para os fãs da FURIA, com foco em visual atraente, personalização de perfil e interatividade. A lógica é toda executada no lado do cliente (client-side), sem backend.
"""


