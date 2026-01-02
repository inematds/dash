# Padrao de Paginas - Dashboard Mastery

Padrao visual e estrutural baseado nos projetos SHIA e NanoBanana.

---

## 1. Menu no Topo

```html
[📊 Dashboard Mastery] | [INEMA.CLUB]
[Trilha 1] [Trilha 2] [Trilha 3] [🌙 Theme]
```

**Elementos:**
- Logo com emoji + nome do curso
- Link externo para INEMA.CLUB
- Botoes das trilhas (ativo com cor, outros neutros)
- Toggle de tema (dark/light)

---

## 2. Topicos Expansiveis com Toggle

**Estrutura:**
```
▸ 🎯 Titulo do Topico - Descricao breve
  └─ O que e: [Explicacao]
  └─ Por que aprender: [Justificativa]
  └─ Conceitos-chave: [Lista]
```

**Comportamento:**
- Seta `▸` vira `▾` ao expandir
- Fecha outros topicos do mesmo modulo ao abrir um novo
- Conteudo oculto com classe `.topic-explanation`
- Toggle via JavaScript `toggleTopic(button)`

---

## 3. Estrutura de Cada Topico

Cada topico DEVE ter 3 secoes internas:

| Secao | Descricao |
|-------|-----------|
| **O que e** | Definicao clara e objetiva do conceito |
| **Por que aprender** | Justificativa e beneficios praticos |
| **Conceitos-chave** | Lista dos pontos principais a memorizar |

**Exemplo:**
```html
<div class="bg-dark-700/50 rounded-lg p-4 space-y-3">
  <div>
    <span class="text-emerald-400 font-semibold">O que e:</span>
    <p class="text-neutral-300 text-sm">Dashboard e uma interface visual...</p>
  </div>
  <div>
    <span class="text-emerald-400 font-semibold">Por que aprender:</span>
    <p class="text-neutral-300 text-sm">Reduz tempo de analise em 80%...</p>
  </div>
  <div>
    <span class="text-emerald-400 font-semibold">Conceitos-chave:</span>
    <p class="text-neutral-300 text-sm">Consolidacao, tempo real, interatividade...</p>
  </div>
</div>
```

---

## 4. Botoes Modal e Completo

Cada modulo tem 2 botoes no rodape:

```html
<div class="p-4 bg-dark-700/30 flex justify-end space-x-3">
  <button onclick="openModal('modal-1-1')">
    📖 Ver em Modal
  </button>
  <a href="modulo-1-1.html">
    📄 Ver Completo
  </a>
</div>
```

**Funcionalidade:**
- **Ver em Modal**: Abre o conteudo completo em overlay (carrega via fetch)
- **Ver Completo**: Navega para a pagina completa do modulo
- Ambos levam para a MESMA pagina de conteudo completo

---

## Estrutura Completa de um Modulo

```html
<!-- Card do Modulo -->
<div class="bg-dark-800 rounded-xl border border-dark-600 mb-6">

  <!-- Header -->
  <div class="p-6 border-b border-dark-600">
    <span class="text-emerald-400 font-bold">1.1</span>
    <span class="text-xs text-neutral-500">~20 min</span>
    <h3>📊 Titulo do Modulo</h3>
    <p>Descricao breve do modulo.</p>
  </div>

  <!-- Topicos Expansiveis -->
  <div class="divide-y divide-dark-600">
    <div class="topic-item">
      <button onclick="toggleTopic(this)">
        ▸ 🎯 Topico 1 - Descricao
      </button>
      <div class="topic-explanation">
        <!-- O que e, Por que aprender, Conceitos-chave -->
      </div>
    </div>
    <!-- Mais topicos... -->
  </div>

  <!-- Botoes -->
  <div class="p-4 bg-dark-700/30 flex justify-end space-x-3">
    <button>📖 Ver em Modal</button>
    <a href="modulo-x-x.html">📄 Ver Completo</a>
  </div>

</div>
```

---

## JavaScript Necessario

```javascript
// Toggle de topicos
function toggleTopic(button) {
  const topicItem = button.closest('.topic-item');
  const explanation = topicItem.querySelector('.topic-explanation');
  const arrow = button.querySelector('.text-emerald-400');

  // Fecha outros do mesmo modulo
  const moduleCard = button.closest('.bg-dark-800');
  moduleCard.querySelectorAll('.topic-explanation.active').forEach(exp => {
    if (exp !== explanation) {
      exp.classList.remove('active');
      exp.previousElementSibling.querySelector('.text-emerald-400').textContent = '▸';
    }
  });

  // Toggle atual
  explanation.classList.toggle('active');
  arrow.textContent = explanation.classList.contains('active') ? '▾' : '▸';
}

// Modal
function openModal(modalId) {
  // Carrega conteudo via fetch e exibe em overlay
}

function closeModal() {
  // Fecha o overlay
}
```

---

## CSS Necessario

```css
.topic-explanation { display: none; }
.topic-explanation.active { display: block; }
```

---

## Cores por Trilha

| Trilha | Cor Principal | Classes |
|--------|---------------|---------|
| Trilha 1 | Emerald | `text-emerald-400`, `bg-emerald-500/20` |
| Trilha 2 | Blue | `text-blue-400`, `bg-blue-500/20` |
| Trilha 3 | Purple | `text-purple-400`, `bg-purple-500/20` |
