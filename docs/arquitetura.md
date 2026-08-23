# Arquitetura e Padrões de Código

Este documento estabelece as regras de escrita e nomenclatura para manter a consistência do nosso repositório.

---

## 1. HTML
* **Padrão:** `kebab-case` (letras minúsculas separadas por hífen) para todos os atributos de identificação e estilização.
* **Tags e Atributos:** Sempre em caixa baixa.
* **Aspas:** Utilize aspas duplas de forma obrigatória.

```html
<!-- Certo -->
<div id="container-principal" class="botao-enviar"></div>

<!-- Errado -->
<div id="ContainerPrincipal" class="Botao_Enviar"></div>
```

---

## 2. CSS
* **Padrão:** `kebab-case` para classes e IDs.
* **Propriedades:** Sempre escritas em letras minúsculas.
* **Valores de Cores:** Utilize a escala Hexadecimal em caixa baixa (reduzida quando possível).

```css
/* Certo */
.caixa-texto {
  color: #333;
  background-color: #ffffff;
}

/* Errado */
.CaixaTexto {
  Color: #333333;
}
```

---

## 3. JavaScript (JS)
* **Variáveis e Funções:** `camelCase` (primeira palavra minúscula, as seguintes com a primeira letra maiúscula).
* **Classes e Componentes:** `PascalCase` (todas as palavras com a primeira letra maiúscula).
* **Constantes Globais:** `UPPER_SNAKE_CASE` (letras maiúsculas separadas por underline).

```javascript
// Certo
const taxaLimite = 10;
const LIMITE_MAXIMO = 100;

function calcularValorTotal() {
  // código
}

class UsuarioAdmin {
  // código
}

// Errado
var taxa_limite = 10;
function Calcular_Valor_Total() {}
```

---

## 4. Arquitetura Estrutural (HTML vs CSS)

A ordem das regras no arquivo CSS deve refletir fielmente a estrutura sequencial do HTML e a hierarquia de especificidade dos seletores.

---

### 4.1. Ordem de Escopo Global e Especificidade
Organize o arquivo CSS do topo para o fundo seguindo estritamente esta ordem de prioridade:

1. **Variáveis Globais (`:root`):** Sempre no topo absoluto do arquivo principal.
2. **Resets e Elementos Gerais (Tags):** Estilizações globais de tags (`body`, `h1`, `p`, `a`). Elas tratam a personalização de forma geral e não específica.
3. **Componentes e Classes:** Estruturas específicas organizadas de acordo com a ordem em que aparecem no HTML.

```css
/* 1. VARIÁVEIS GLOBAIS */
:root {
  --cor-primaria: #007bff;
}

/* 2. TAGS GERAIS (BAIXA ESPECIFICIDADE) */
body {
  font-family: Arial, sans-serif;
  margin: 0;
}

h1 {
  color: #333;
}

/* 3. CLASSES ESPECÍFICAS (ALTA ESPECIFICIDADE) */
.cabecalho-principal { ... }
.conteudo-artigo { ... }
```

---

### 4.2. Alinhamento Sequencial (HTML x CSS)
Não pule a ordem dos elementos. Se um elemento `A` aparece antes do elemento `B` no HTML, a classe do elemento `A` **deve** vir antes da classe do elemento `B` no arquivo CSS.

```html
<!-- Sequência no HTML -->
<header class="cabecalho"></header>
<main class="conteudo-principal"></main>
<footer class="rodape"></footer>
```

```css
/* Sequência Correta no CSS */
.cabecalho { ... }
.conteudo-principal { ... }
.rodape { ... }

/* Incorreto: Evite espelhar as classes fora de ordem */
.rodape { ... }
.cabecalho { ... }
.conteudo-principal { ... }
```
