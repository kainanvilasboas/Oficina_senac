# Documentação de Alterações - Projeto Oficina Senac
**Data:** 30 de Abril de 2026
**Responsável:** Antigravity (Desenvolvedor Frontend Sênior)

---

## 🚀 Resumo do Dia
Hoje focamos em transformar o site em uma estrutura mais profissional, modular e visualmente dinâmica. As principais frentes foram a **centralização da navegação** e a implementação de **efeitos de revelação ao rolar a página**.

---

## 1. Sistema de Animação "Scroll Reveal"
Implementamos um sistema que faz as seções do site aparecerem suavemente conforme o usuário desce a página.

- **Tecnologia:** Utilização da API `IntersectionObserver` para máxima performance (não sobrecarrega o navegador).
- **CSS:** Criadas as classes `.revelar` (estado inicial escondido) e `.revelar.ativo` (estado visível) no arquivo `assets/css/microframework.os`.
- **JS:** Lógica centralizada em `assets/js/script.js` que monitora a entrada de elementos na tela e aplica a classe de ativação.
- **Aplicação:** Aplicado em `index.html`, `projetos.html` e `servicos.html`.

## 2. Centralização da Navbar (Source of Truth)
Resolvemos o problema de ter que editar o menu em vários arquivos HTML diferentes. Agora existe apenas um local de alteração.

- **Novo Arquivo:** `assets/js/navbar.js`.
- **Estrutura Dinâmica:** O menu agora é injetado via JavaScript nos contêineres:
  - `<div id="cabecalho-global"></div>`: Barra de contatos e redes sociais.
  - `<div id="menu-navegacao"></div>`: Barra de links de navegação.
- **Destaque de Link Ativo:** O script agora identifica automaticamente em qual página o usuário está e aplica a classe `bem-navbar__link--active` ao link correspondente.

## 3. Padronização de Nomenclatura (BEM em Português)
Conforme solicitado, todas as novas classes e lógicas foram nomeadas em português para facilitar a leitura e manutenção.

- **Exemplos de Classes:**
  - `.revelar` em vez de `.reveal`
  - `.ativo` em vez de `.active`
  - `#cabecalho-global` em vez de `#global-header`

## 4. Limpeza de Código Legado
- Removidos blocos de navegação estáticos (mais de 100 linhas por arquivo HTML).
- Limpeza no `assets/css/style.css`, movendo estilos globais para o `microframework.css`.
- Remoção de códigos comentados que não eram mais utilizados.

---

## 📂 Arquivos Impactados
| Arquivo | Descrição da Mudança |
| :--- | :--- |
| `index.html` | Inclusão de IDs de injeção e classes de revelação. |
| `projetos.html` | Centralização da navbar e ativação de animações. |
| `servicos.html` | Centralização da navbar e ativação de animações. |
| `assets/js/navbar.js` | **Novo arquivo.** Responsável pelo menu único do site. |
| `assets/js/script.js` | Implementação do IntersectionObserver (Revelação). |
| `assets/css/microframework.css` | Definição das animações de transição e opacidade. |
| `assets/css/style.css` | Limpeza de classes redundantes. |

---

## 💡 Dicas para Próximas Alterações
- **Para adicionar um novo link no menu:** Altere apenas o arquivo `assets/js/navbar.js`.
- **Para fazer uma nova seção animar ao entrar na tela:** Basta adicionar a classe `revelar` na tag HTML da seção.

---
*Documentação gerada automaticamente para registro de progresso.*
