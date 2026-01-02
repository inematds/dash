# Layout Reference - Supercurso Nano Banana

Documentação do sistema de layout e design utilizado nas páginas de conteúdo do curso.

---

## 1. Estrutura Base HTML

```html
<!DOCTYPE html>
<html lang="pt-BR" class="dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Título do Módulo] | TikTok Shop Academy 2025</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            primary: '#CDDC39',
            accent: '#E040FB',
            dark: { 900: '#111827', 800: '#1f2937', 700: '#374151', 600: '#4b5563' }
          }
        }
      }
    }
  </script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Inter', sans-serif; }
    .dark body { background-color: #111827; }
    html:not(.dark) body { background-color: #f8fafc; }
    html:not(.dark) .bg-dark-900 { background-color: #f8fafc !important; }
    html:not(.dark) .bg-dark-800 { background-color: #ffffff !important; }
    html:not(.dark) .bg-dark-700 { background-color: #f1f5f9 !important; }
    html:not(.dark) .border-dark-600 { border-color: #e2e8f0 !important; }
    html:not(.dark) .text-neutral-100 { color: #1e293b !important; }
    html:not(.dark) .text-neutral-200 { color: #334155 !important; }
    html:not(.dark) .text-neutral-300 { color: #475569 !important; }
    html:not(.dark) .text-neutral-400 { color: #64748b !important; }
  </style>
</head>
<body class="bg-dark-900 text-neutral-100 min-h-screen">
  <!-- Conteúdo aqui -->

  <script>
    // Theme initialization
    if (localStorage.getItem('color-theme') === 'light') {
      document.documentElement.classList.remove('dark');
    } else {
      document.documentElement.classList.add('dark');
    }
  </script>
</body>
</html>
```

---

## 2. Paleta de Cores

### Dark Mode (Padrão)
| Nome | Código | Uso |
|------|--------|-----|
| `dark-900` | `#111827` | Fundo principal da página |
| `dark-800` | `#1f2937` | Cards, containers |
| `dark-700` | `#374151` | Elementos internos, hover states |
| `dark-600` | `#4b5563` | Bordas, divisores |

### Light Mode
| Nome | Código | Uso |
|------|--------|-----|
| Background | `#f8fafc` | Fundo principal |
| Cards | `#ffffff` | Cards, containers |
| Elementos | `#f1f5f9` | Elementos internos |
| Bordas | `#e2e8f0` | Bordas, divisores |

### Cores de Destaque
| Nome | Código | Uso |
|------|--------|-----|
| `primary` | `#CDDC39` | CTAs, destaques principais, botões |
| `accent` | `#E040FB` | Elementos secundários, badges |

### Cores Semânticas (Tailwind)
| Cor | Uso |
|-----|-----|
| `emerald-400/500` | Sucesso, positivo, "fazer" |
| `red-400/500` | Erro, alerta, "não fazer" |
| `blue-400/500` | Informação, dados |
| `yellow-400/500` | Aviso, atenção, logo Nano Banana |
| `purple-400/500` | Especial, premium |
| `cyan-400/500` | Tech, inovação |
| `sky-400/500` | Links externos (INEMA.CLUB) |
| `pink-400/500` | Beleza, feminino |
| `orange-400/500` | Energia, urgência |
| `amber-400/500` | Destaque suave |

---

## 3. Componentes de Layout

### 3.1 Navigation Global (Sticky Top)

> ⚠️ **OBRIGATÓRIO**: O menu global DEVE aparecer em **TODAS as páginas** do curso, sem exceção.

#### Elementos Obrigatórios do Menu:

1. **Logo SHIA** (🧠) - Link para index.html
2. **INEMA.CLUB** - Link externo OBRIGATÓRIO em sky-400, abre em nova aba
3. **Links para TODAS as 4 Trilhas** (0, 1, 2, 3) - Sempre visíveis
4. **Theme Toggle** - Botão para alternar dark/light mode

```html
<!-- Navigation Global - OBRIGATÓRIO EM TODAS AS PÁGINAS -->
<nav class="sticky top-0 z-50 bg-dark-900/95 backdrop-blur-sm border-b border-dark-600">
  <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center h-14">
      <!-- Logo + INEMA.CLUB (OBRIGATÓRIO) -->
      <div class="flex items-center space-x-3">
        <a href="../../index.html" class="flex items-center space-x-2 text-yellow-400 hover:text-yellow-300 transition-colors">
          <span class="text-2xl">🧠</span>
          <span class="font-bold text-lg hidden sm:inline">SHIA</span>
        </a>
        <span class="text-neutral-500 hidden sm:inline">|</span>
        <a href="http://inema.club" target="_blank" class="text-sky-400 hover:text-sky-300 font-bold text-lg hidden sm:inline transition-colors">
          INEMA.CLUB
        </a>
      </div>

      <!-- TODAS as 4 Trilhas + Theme Toggle (OBRIGATÓRIO) -->
      <div class="flex items-center space-x-1 sm:space-x-2">
        <!-- Trilha 0 - Amarelo -->
        <a href="curso/trilha0/trilha01.html" class="px-3 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-yellow-400 hover:bg-yellow-500/10 transition-colors">
          <span class="hidden sm:inline">Trilha </span>0
        </a>
        <!-- Trilha 1 - Verde -->
        <a href="curso/trilha1/trilha11.html" class="px-3 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-emerald-400 hover:bg-emerald-500/10 transition-colors">
          <span class="hidden sm:inline">Trilha </span>1
        </a>
        <!-- Trilha 2 - Azul -->
        <a href="curso/trilha2/trilha21.html" class="px-3 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-blue-400 hover:bg-blue-500/10 transition-colors">
          <span class="hidden sm:inline">Trilha </span>2
        </a>
        <!-- Trilha 3 - Roxo -->
        <a href="curso/trilha3/trilha31.html" class="px-3 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-purple-400 hover:bg-purple-500/10 transition-colors">
          <span class="hidden sm:inline">Trilha </span>3
        </a>

        <!-- Theme Toggle -->
        <button id="theme-toggle" class="p-2 rounded-lg bg-dark-700 hover:bg-dark-600 transition-colors ml-2">
          <!-- SVG icons para dark/light mode -->
        </button>
      </div>
    </div>
  </div>
</nav>
```

#### Cores das Trilhas (OBRIGATÓRIO)

| Trilha | Cor | Classes Ativa | Classes Inativa |
|--------|-----|---------------|-----------------|
| **Trilha 0** | Amarelo | `bg-yellow-500/20 text-yellow-400 border border-yellow-500/30` | `text-neutral-400 hover:text-yellow-400 hover:bg-yellow-500/10` |
| **Trilha 1** | Verde | `bg-emerald-500/20 text-emerald-400 border border-emerald-500/30` | `text-neutral-400 hover:text-emerald-400 hover:bg-emerald-500/10` |
| **Trilha 2** | Azul | `bg-blue-500/20 text-blue-400 border border-blue-500/30` | `text-neutral-400 hover:text-blue-400 hover:bg-blue-500/10` |
| **Trilha 3** | Roxo | `bg-purple-500/20 text-purple-400 border border-purple-500/30` | `text-neutral-400 hover:text-purple-400 hover:bg-purple-500/10` |

**Propriedades:**
- Posição: `sticky top-0`
- Z-index: `50`
- Altura: `h-14` (56px)
- Background: `bg-dark-900/95 backdrop-blur-sm`
- Logo: 🧠 SHIA (yellow-400)
- **INEMA.CLUB**: OBRIGATÓRIO - Link externo em sky-400 (azul claro), separado por `|`, abre em nova aba
- **4 Trilhas**: OBRIGATÓRIO - Todas sempre visíveis no menu
- Trilha ativa: fundo e borda coloridos
- Responsivo: texto compacto em mobile

### 3.2 Header do Módulo
```html
<div class="text-center mb-12">
  <span class="inline-block px-4 py-2 bg-[COR]-500/20 text-[COR]-400 rounded-full text-sm font-semibold mb-4">
    MÓDULO X - CATEGORIA
  </span>
  <h1 class="text-4xl sm:text-5xl font-bold mb-4">[EMOJI] Título do Módulo</h1>
  <p class="text-xl text-neutral-400 max-w-2xl mx-auto">
    Descrição breve do módulo em 1-2 linhas.
  </p>
</div>
```

### 3.3 Stats Banner (Métricas)
```html
<div class="grid grid-cols-3 gap-4 mb-12">
  <div class="bg-dark-800 rounded-xl p-4 text-center border border-dark-600">
    <div class="text-2xl font-bold text-[COR]-400">XX</div>
    <div class="text-xs text-neutral-400">Label</div>
  </div>
  <!-- Repetir para cada métrica -->
</div>
```

### 3.4 Section com Gradiente
```html
<section class="mb-12">
  <div class="bg-gradient-to-br from-[COR]-900/30 to-dark-800 rounded-2xl p-8 border border-[COR]-500/30">
    <div class="flex items-center mb-6">
      <span class="text-4xl mr-4">[EMOJI]</span>
      <div>
        <h2 class="text-2xl font-bold text-[COR]-400">Título da Seção</h2>
        <p class="text-neutral-400">Subtítulo explicativo</p>
      </div>
    </div>
    <!-- Conteúdo -->
  </div>
</section>
```

### 3.5 Section Simples (Card)
```html
<section class="mb-12">
  <div class="bg-dark-800 rounded-2xl p-8 border border-dark-600">
    <div class="flex items-center mb-6">
      <span class="text-4xl mr-4">[EMOJI]</span>
      <div>
        <h2 class="text-2xl font-bold text-neutral-100">Título</h2>
        <p class="text-neutral-400">Subtítulo</p>
      </div>
    </div>
    <!-- Conteúdo -->
  </div>
</section>
```

### 3.6 Box de Informação Interna
```html
<div class="bg-dark-700/50 rounded-xl p-6 mb-6">
  <h3 class="text-xl font-bold text-[COR]-400 mb-4">[EMOJI] Título</h3>
  <!-- Conteúdo -->
</div>
```

### 3.7 Alerta/Destaque Colorido
```html
<div class="bg-[COR]-900/20 p-6 rounded-xl border border-[COR]-500/30">
  <h4 class="font-bold text-[COR]-400 mb-3">[EMOJI] Título</h4>
  <p class="text-neutral-300">Conteúdo do alerta...</p>
</div>
```

### 3.8 Grid de Comparação (Fazer/Não Fazer)
```html
<div class="grid md:grid-cols-2 gap-6 mb-6">
  <div class="bg-emerald-900/20 p-6 rounded-xl border border-emerald-500/30">
    <h4 class="font-bold text-emerald-400 mb-4">✓ O que FAZER</h4>
    <ul class="space-y-3 text-neutral-300">
      <li class="flex items-start">
        <span class="text-emerald-400 mr-2">✓</span>
        <span>Item positivo</span>
      </li>
    </ul>
  </div>
  <div class="bg-red-900/20 p-6 rounded-xl border border-red-500/30">
    <h4 class="font-bold text-red-400 mb-4">✗ O que NÃO fazer</h4>
    <ul class="space-y-3 text-neutral-300">
      <li class="flex items-start">
        <span class="text-red-400 mr-2">✗</span>
        <span>Item negativo</span>
      </li>
    </ul>
  </div>
</div>
```

### 3.9 Timeline/Passos Numerados
```html
<div class="flex items-start mb-8">
  <div class="w-16 h-16 bg-[COR]-500 rounded-full flex items-center justify-center text-white font-bold text-lg mr-4">
    1
  </div>
  <div>
    <h4 class="text-xl font-bold text-[COR]-400">Título do Passo</h4>
    <p class="text-neutral-400">Descrição</p>
  </div>
</div>
```

### 3.10 Barra de Progresso
```html
<div>
  <div class="flex justify-between mb-1">
    <span class="text-sm text-neutral-300">Label</span>
    <span class="text-sm text-[COR]-400">XX%</span>
  </div>
  <div class="w-full bg-dark-600 rounded-full h-4">
    <div class="bg-[COR]-500 h-4 rounded-full" style="width: XX%"></div>
  </div>
</div>
```

### 3.11 Checklist Interativo
```html
<div class="flex items-center bg-dark-800/50 p-3 rounded-lg">
  <input type="checkbox" class="mr-3 w-5 h-5 accent-primary">
  <span class="text-neutral-300">Item do checklist</span>
</div>
```

### 3.12 Tabela
```html
<div class="overflow-x-auto">
  <table class="w-full text-sm">
    <thead>
      <tr class="border-b border-dark-600">
        <th class="text-left py-3 px-4 text-neutral-400">Coluna 1</th>
        <th class="text-left py-3 px-4 text-neutral-400">Coluna 2</th>
      </tr>
    </thead>
    <tbody class="text-neutral-300">
      <tr class="border-b border-dark-700">
        <td class="py-3 px-4">Dado 1</td>
        <td class="py-3 px-4">Dado 2</td>
      </tr>
    </tbody>
  </table>
</div>
```

### 3.13 CTA Final / Resumo
```html
<section class="mb-12">
  <div class="bg-primary/10 rounded-2xl p-8 border border-primary/30">
    <h2 class="text-2xl font-bold text-primary mb-6 text-center">[EMOJI] Título do Resumo</h2>
    <!-- Conteúdo -->
    <div class="text-center mt-8">
      <a href="../index.html" class="inline-flex items-center space-x-2 px-6 py-3 bg-primary text-dark-900 rounded-lg font-bold hover:bg-primary/90 transition-colors">
        <span>Voltar para o Curso</span>
        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
        </svg>
      </a>
    </div>
  </div>
</section>
```

### 3.14 Footer
```html
<footer class="bg-dark-900 border-t border-dark-700 py-8">
  <div class="max-w-4xl mx-auto px-4 text-center">
    <p class="text-neutral-500 text-sm">
      TikTok Shop Academy 2025 - [Nome do Módulo]
    </p>
  </div>
</footer>
```

---

## 4. Padrões de Espaçamento

| Classe | Uso |
|--------|-----|
| `mb-12` | Entre seções principais |
| `mb-6` | Entre sub-seções |
| `mb-4` | Entre elementos dentro de uma seção |
| `mb-2` | Entre linhas de texto |
| `p-8` | Padding de cards principais |
| `p-6` | Padding de boxes internos |
| `p-4` | Padding de elementos menores |
| `p-3` | Padding de itens de lista |
| `gap-4` | Espaço entre itens de grid |
| `gap-6` | Espaço maior entre itens de grid |
| `space-y-3` | Espaço vertical entre itens de lista |

---

## 5. Tipografia

| Elemento | Classes |
|----------|---------|
| Título da página (h1) | `text-4xl sm:text-5xl font-bold` |
| Título de seção (h2) | `text-2xl font-bold` |
| Título de sub-seção (h3) | `text-xl font-bold` |
| Título pequeno (h4) | `font-bold` ou `font-semibold` |
| Parágrafo destaque | `text-lg text-neutral-300` |
| Parágrafo normal | `text-neutral-300` |
| Texto secundário | `text-neutral-400` |
| Texto pequeno | `text-sm text-neutral-300` |
| Texto muito pequeno | `text-xs text-neutral-400` |
| Badge/Tag | `text-sm font-semibold` |

---

## 6. Container Principal

Todas as páginas usam `max-w-4xl` para largura máxima do conteúdo:

```html
<main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
  <!-- Conteúdo -->
</main>
```

---

## 7. Responsividade

- Grid de 2 colunas: `grid md:grid-cols-2`
- Grid de 3 colunas: `grid md:grid-cols-3`
- Grid de 4 colunas: `grid grid-cols-2 md:grid-cols-4`
- Texto responsivo: `text-4xl sm:text-5xl`
- Padding responsivo: `px-4 sm:px-6 lg:px-8`

---

## 8. Efeitos Visuais

| Efeito | Classes |
|--------|---------|
| Blur no background | `backdrop-blur-sm` |
| Transparência | `bg-dark-900/95` (95% opacidade) |
| Gradiente | `bg-gradient-to-br from-[cor]-900/30 to-dark-800` |
| Hover em link | `hover:text-primary transition-colors` |
| Hover em botão | `hover:bg-primary/90 transition-colors` |
| Borda colorida à esquerda | `border-l-4 border-[cor]-500` |

---

## 9. Emojis por Categoria

| Categoria | Emojis Sugeridos |
|-----------|------------------|
| Mentalidade | 🧠 💡 ⏰ ✨ 🎯 |
| Algoritmo | ⚙️ 🤖 📊 🔄 🎯 |
| Tempo | ⏱️ 🏗️ 🔄 ⚡ 📐 |
| Conteúdo | 🎬 📋 🪝 ✓ |
| Gatilhos | 💡 😲 ✓ 🎯 💭 ⭐ |
| Roteiros | 📝 🏠 💄 👗 🎧 🧹 |
| Sucesso | ✅ ✓ 🎉 🚀 |
| Alerta | ⚠️ ❌ ✗ |
| Info | 📊 📈 💡 ℹ️ |

---

## 10. Especificações de Imagens

> ⚠️ **OBRIGATÓRIO**: Todas as imagens do projeto devem seguir estas especificações para garantir performance.

### Formato e Otimização

| Propriedade | Valor | Descrição |
|-------------|-------|-----------|
| **Formato** | WebP | Obrigatório - melhor compressão |
| **Largura máxima** | 1200px | Redimensionar imagens maiores |
| **Qualidade** | 80 | Balanço entre qualidade e tamanho |
| **Otimização** | optimize=True | Usar compressão otimizada |

### Script de Otimização (Python/Pillow)

```python
from PIL import Image
import os

def optimize_image(filepath, max_width=1200, quality=80):
    img = Image.open(filepath)

    # Redimensiona se maior que max_width
    if img.size[0] > max_width:
        ratio = max_width / img.size[0]
        new_height = int(img.size[1] * ratio)
        img = img.resize((max_width, new_height), Image.LANCZOS)

    # Salva como WebP otimizado
    output_path = filepath.rsplit('.', 1)[0] + '.webp'
    img.save(output_path, 'WEBP', quality=quality, optimize=True)
    return output_path
```

### Estrutura de Pastas de Imagens

```
doc/imagens/
├── geral/           # Imagens da página principal
├── introducao/      # Trilha 0
├── arte/            # Trilha 1
├── engenharia/      # Trilha 2
└── educadores/      # Trilha 3
```

### Uso em HTML

```html
<img
  src="doc/imagens/geral/nome_imagem.webp"
  alt="Descrição acessível da imagem"
  class="w-full max-w-4xl mx-auto rounded-2xl shadow-xl border border-dark-600/50"
/>
```

### Checklist de Imagens

- [ ] Formato WebP (não PNG/JPG)
- [ ] Largura máxima 1200px
- [ ] Qualidade 80
- [ ] Alt text descritivo
- [ ] Classes de estilo consistentes

---

## 11. Checklist de Criação de Página

- [ ] Estrutura HTML base com Tailwind config
- [ ] Navigation sticky com INEMA.CLUB e 4 trilhas (OBRIGATÓRIO)
- [ ] Header com badge, título e descrição
- [ ] Stats banner (se aplicável)
- [ ] Seções com gradiente para conceitos principais
- [ ] Boxes de comparação (fazer/não fazer)
- [ ] Alertas coloridos para dicas
- [ ] Resumo final com CTA
- [ ] Footer
- [ ] Script de inicialização do tema
- [ ] Verificar responsividade
- [ ] Verificar dark/light mode
- [ ] Imagens otimizadas (WebP, 1200px, quality 80)
