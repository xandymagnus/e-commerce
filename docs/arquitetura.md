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
