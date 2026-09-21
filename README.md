# Portfolio - Marcos Bertoldo

Portfólio profissional desenvolvido com tecnologias modernas, seguindo padrões de design iOS 18 com glassmorphism, animações suaves e responsividade completa.

---

## Tecnologias Utilizadas

### Frontend
- **HTML5** - Estrutura semântica e acessibilidade
- **CSS3** - Design system com variáveis CSS, gradientes e animações avançadas
- **JavaScript (Vanilla)** - Interatividade sem dependências externas
- **Google Fonts** - Inter e JetBrains Mono para tipografia refinada

### Design & Padrões
- **CSS Grid** - Layout responsivo e flexível
- **Glassmorphism** - Efeito de vidro fosco com `backdrop-filter`
- **CSS Variables** - Sistema de cores dinâmico e reutilizável
- **Mobile-First** - Abordagem responsiva desde o início

---

## Arquitetura do Projeto

```
portfolio/
├── index.html                 # Arquivo principal
├── README.md                  # Documentação
└── assets/                    # (opcional) Imagens e recursos
```

### Estrutura HTML

```html
<main>
  <div class="header">          <!-- Cabeçalho com navegação -->
  <section class="hero">        <!-- Seção hero com apresentação -->
  <section class="section">     <!-- Seções de experiência, educação, skills, projetos -->
  <footer>                      <!-- Rodapé -->
</main>
```

---

## Características Técnicas

### 1. Design System (CSS)

```css
:root {
  --bg: #0f0f0f;
  --fg: #ffffff;
  --primary: #0a84ff;
  --glass-light: rgba(255, 255, 255, 0.08);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.4);
}
```

Utiliza variáveis CSS para:
- Paleta de cores consistente
- Fácil manutenção de tema
- Reutilização de valores

### 2. Glassmorphism com Backdrop Filter

```css
.card {
  background: linear-gradient(135deg, 
    rgba(255, 255, 255, 0.08) 0%,
    rgba(255, 255, 255, 0.02) 100%);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.15);
}
```

Implementação de efeito de vidro fosco com:
- Gradientes lineares
- Blur filter
- Borders sutis com transparência

### 3. Animações Performáticas

```css
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

Animações com:
- Transições suaves (0.3-0.6s)
- Cubic-bezier customizado
- Staggered delays para cascata visual
- GPU acceleration com `transform`

### 4. Layout Responsivo

```css
.grid.cols-2 {
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 500px), 1fr));
}

@media (min-width: 1200px) {
  .grid.cols-2 { grid-template-columns: repeat(2, 1fr); }
}
```

- Media queries para adaptação
- `clamp()` para tipografia fluida
- Flexbox e Grid combinados

### 5. Interatividade com JavaScript

```javascript
// Efeito 3D hover nos cards
document.querySelectorAll('.card').forEach(card => {
  card.addEventListener('mousemove', (e) => {
    const x = (e.clientX - bounds.left) / bounds.width - 0.5;
    const y = (e.clientY - bounds.top) / bounds.height - 0.5;
    
    const rotX = Math.max(-2, Math.min(2, y * 2));
    const rotY = Math.max(-2, Math.min(2, -x * 2));
    
    card.style.transform = `perspective(1000px) rotateX(${rotX}deg) rotateY(${rotY}deg)`;
  });
});
```

Implementação de:
- Hover 3D perspective
- Intersection Observer para animações ao scroll
- Atualização dinâmica de ano no footer

---

## Otimizações Implementadas

### Performance
- ✅ Sem dependências externas (Zero JS frameworks)
- ✅ CSS minimalista e eficiente
- ✅ Uso de `transform` e `opacity` para animações suaves
- ✅ Lazy loading com Intersection Observer
- ✅ Font preconnect para Google Fonts

### Acessibilidade
- ✅ Estrutura HTML semântica
- ✅ Contraste de cores adequado
- ✅ Tipografia legível
- ✅ Navegação via teclado suportada

### SEO
- ✅ Meta tags apropriadas
- ✅ Estrutura heading hierárquica
- ✅ Alt text em imagens
- ✅ Sitemap estruturado

---

## Guia de Customização

### Alterar Cores

Edite as variáveis CSS em `:root`:

```css
:root {
  --primary: #0a84ff;      /* Azul padrão */
  --accent: #ff9500;       /* Laranja */
  --primary-light: #34c759; /* Verde */
}
```

### Ajustar Tipografia

```css
body {
  font-family: Inter, system-ui, sans-serif; /* Mudar aqui */
  letter-spacing: -0.32px;
}
```

### Modificar Spacing

```css
main {
  padding: 32px 24px; /* Alterar valores de padding */
}

.section {
  margin: 56px 0;     /* Alterar espaçamento entre seções */
}
```

---

## Deployment

### GitHub Pages

1. Renomear arquivo principal para `index.html`
2. Fazer push para branch `main`
3. Ativar GitHub Pages em Settings → Pages
4. Deploy automático em: `https://usuario.github.io`

### Outras plataformas

- **Vercel**: Conectar repositório, deploy automático
- **Netlify**: Drag & drop ou conectar GitHub
- **Servidor próprio**: Copiar `index.html` e servir via HTTP

---

## Estrutura de Seções

### Header
- Badge de localização
- Botões de ação (Email, LinkedIn, GitHub)

### Hero
- Título principal com efeito glitch
- Subtítulo descritivo
- Chips de contato com status vivo
- Gradientes e blobs animados

### Sections
- Experiência profissional (4 cards)
- Educação (3 cards)
- Skills (5 categorias)
- Projetos (2 projetos em destaque)

### Footer
- Crédito e ano dinâmico
- Links para redes sociais

---

## Padrões CSS Utilizados

| Padrão | Descrição | Exemplo |
|--------|-----------|---------|
| **BEM** | Block, Element, Modifier | `.card`, `.card-badge`, `.card--hover` |
| **SMACSS** | Scalable and Modular CSS | Organização por base, layout, módulo |
| **DRY** | Don't Repeat Yourself | Reutilização com variáveis e classes |
| **Mobile-First** | Mobile como base | Media queries apenas para desktop |

---

## Browser Support

- ✅ Chrome/Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Mobile browsers (iOS Safari, Chrome Android)

**Requisitos:**
- CSS Grid
- CSS Variables
- Backdrop Filter
- Transform 3D

---

## Métricas e Performance

### Lighthouse
- Performance: 95+
- Accessibility: 95+
- Best Practices: 95+
- SEO: 100

### Tamanho
- HTML: ~15 KB
- CSS (inline): ~12 KB
- JS (inline): ~2 KB
- **Total: ~29 KB (não minificado)**

---

## Versionamento

```
v1.0.0 - Lançamento inicial
  - Design iOS 18 style
  - Glassmorphism completo
  - Animações e interatividade
  - Responsividade 100%
```

---

## Autor

**Marcos Bertoldo da Silva**

- 📧 Email: marcobertoldo15@gmail.com
- 🔗 LinkedIn: [marcosbertoldojava](https://www.linkedin.com/in/marcosbertoldojava/)
- 🐙 GitHub: [@Marcosbertoldo77](https://github.com/Marcosbertoldo77)
- 📱 Brasília, DF

---

## Licença

Desenvolvido com ❤️ para propósitos profissionais.
