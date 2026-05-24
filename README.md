# Cardápio Digital — Padaria da Eli

Cardápio digital de balcão para a **Padaria da Eli** (Pães e Doces — Desde 1998), otimizado para carregamento instantâneo em conexões 3G/4G instáveis na fila do caixa.

## Visão geral

- **Arquivo único** (`index.html`) — HTML, CSS e JavaScript inline, sem build step
- **Zero dependências externas** — sem CDN, sem frameworks, sem fontes externas
- **~16 KB** de peso total — carrega em menos de 1 segundo até em 3G
- **Mobile-first** com suporte a dark mode automático (`prefers-color-scheme`)
- **Acessível** — ARIA labels, tap targets de 44px (WCAG 2.5.5), alto contraste

## Funcionalidades

- Navegação rápida por categorias via pills horizontais
- Seção de destaque para Combos do Dia
- Botão "voltar ao topo" (aparece ao rolar)
- Preços alinhados em coluna à direita para leitura rápida
- Scroll suave com compensação do header sticky
- Rodapé com telefone clicável (`tel:`)
- Fallback `<noscript>` para navegadores sem JavaScript

## Como editar o cardápio

Abra o `index.html` e localize a **Área de Edição Rápida** no início do bloco `<script>` (por volta da linha 160). A estrutura é autoexplicativa:

```javascript
// Dados da loja
var LOJA = { nome: "...", tel: "...", endereco: "..." };

// Combos em destaque
var COMBOS = [
  { nome: "Combo Café", desc: "Misto Quente + Café", preco: "14,00" },
];

// Categorias do cardápio
var CATEGORIAS = [
  {
    titulo: "🥖 Panificação",
    itens: [
      { nome: "Pão Francês", desc: "por kg", preco: "20,49" },
    ]
  },
];
```

| Ação | Como fazer |
|------|-----------|
| Alterar um preço | Mude o valor entre aspas (ex: `"20,49"` → `"22,00"`) |
| Adicionar um item | Copie uma linha `{ nome, preco }` e cole na categoria desejada |
| Criar nova categoria | Copie um bloco `{ titulo, itens: [...] }` inteiro |
| Remover um item | Apague a linha inteira (incluindo a vírgula) |

> O campo `desc` é opcional. Omita se o item não precisar de descrição.

## Deploy

O projeto está hospedado no **GitHub Pages** e faz deploy automático a cada push na branch principal.

```
https://brunotiyoda.github.io/padariadaeli/
```

Para deploy manual:

```bash
git add index.html
git commit -m "atualiza preços"
git push
```

O site atualiza em 1-2 minutos.

## Estrutura do projeto

```
.
└── index.html    # Aplicação completa (HTML + CSS + JS)
```

## Paleta de cores

Derivada da logo da Padaria da Eli:

| Variável | Light | Dark | Uso |
|----------|-------|------|-----|
| `--bg` | `#FFF9F0` | `#1A0E06` | Fundo da página |
| `--text` | `#3E1708` | `#F5E6D0` | Texto principal / header |
| `--accent` | `#7B2D12` | `#D4874A` | Bordas de categoria, botões |
| `--price` | `#6B1D0A` | `#D4A234` | Cor dos preços |
| `--combo-border` | `#C4922A` | `#C4922A` | Destaque dos combos (dourado) |

## Licença

Projeto privado — Padaria da Eli © 2026.
