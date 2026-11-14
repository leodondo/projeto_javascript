# Projeto Java Script - Desenvolvimento Front-End para WEB

## Tema

Página **"Descubra seu caminho no Front-End"**: o visitante informa o nome, escolhe uma área de interesse (HTML, CSS ou JavaScript) e recebe uma orientação personalizada na própria página. Também é possível alternar entre tema claro e escuro.

## Integrantes

Leonardo Hiroshi Dondo de Freitas - RGM: 46610049

## Estrutura de arquivos

```
projeto3_javascript/
├── index.html
├── README.md
├── css/
│   └── estilo.css
└── js/
    └── script.js
```

## Comandos JavaScript utilizados

| `document.getElementById()` | Localiza o campo de nome, o select, os botões e a área de resultado. |
| `const` | Guarda os elementos e valores que não mudam de referência (ex.: `campoNome`, `botaoGerar`). |
| `let` | Guarda a variável `mensagem`, que recebe um texto diferente conforme a escolha. |
| `addEventListener('click', ...)` | Executa uma função quando o botão "Gerar orientação" ou "Alterar tema" é clicado. |
| `.value` | Lê o que foi digitado no campo de nome e a opção escolhida no select. |
| `.trim()` | Remove espaços no início e no fim do nome, evitando aceitar um nome só com espaços. |
| `if` | Valida o nome: se estiver vazio, mostra uma orientação para preenchê-lo e interrompe a função. |
| `switch` | Escolhe a mensagem correta para HTML, CSS ou JavaScript. |
| Template string `` `Olá, ${nome}!` `` | Insere o nome do visitante dentro da mensagem. |
| `.textContent` | Exibe a mensagem dentro da área de resultado da própria página. |
| `function` | Organiza o código em blocos reutilizáveis (`montarOrientacao`, `gerarOrientacao`, `alternarTema`). |
| `.classList.add()` / `.remove()` | Liga e desliga o estilo de erro na área de resultado e no campo de nome. |
| `.classList.toggle()` | Adiciona ou remove a classe `tema-escuro` no `body`, alternando o tema. |

## Como funciona

1. **Carregamento:** o `script.js` localiza os elementos pelo `id` e guarda cada um em uma constante.
2. **Clique em "Gerar orientação":** o evento `click` chama a função `gerarOrientacao()`.
3. **Leitura e validação:** a função lê o nome com `.value.trim()`. Se estiver vazio, exibe uma mensagem de erro na área de resultado e coloca o foco no campo.
4. **Decisão:** se o nome é válido, a função `montarOrientacao()` usa um `switch` para escolher a mensagem conforme a área de interesse e monta o texto com template string.
5. **Exibição:** o texto é colocado na área de resultado com `.textContent`.
6. **Troca de tema:** o botão "Alterar tema" usa `classList.toggle('tema-escuro')` no `body`. No CSS, essa classe redefine as variáveis de cor (`--cor-fundo`, `--cor-texto` etc.), mudando toda a página.

## Testes realizados

- Nome vazio → aparece mensagem de erro orientando o preenchimento.
- Nome só com espaços → tratado como vazio.
- Cada área (HTML, CSS, JavaScript) → gera uma mensagem diferente.
- Botão de tema → alterna entre claro e escuro, várias vezes.
- Tela pequena (≤ 600 px) → layout se adapta, botões ocupam a largura toda.
