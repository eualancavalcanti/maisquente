# Arquitetura do Funil de Redirecionamento

## Visão Geral da Cadeia

```
Instagram (Bio) → meulink.ae → maisquente.com.br → hotboys.com.br
```

---

## CAMADA 1: Instagram (Origem)

### O que é permitido no perfil:
- Bio com linguagem neutra: "Entretenimento adulto premium"
- Link único para meulink.ae
- Conteúdo de feed: lifestyle, bastidores (sem nudez ou sugestão)
- Stories: previews neutros, enquetes genéricas
- Reels: conteúdo de marca, branding

### O que NÃO fazer:
- Não usar termos como "nude", "xxx", "conteúdo sexual", "gostoso"
- Não postar imagens com nudez parcial ou sugestiva
- Não usar CTAs como "assine para ver tudo"
- Não mencionar o nome do site final na bio ou posts
- Não usar hashtags explícitas

### Copy sugerida para bio:
```
🎬 Entretenimento & Lifestyle
📍 Produções originais brasileiras
🔗 Acesse nosso hub ↓
```

---

## CAMADA 2: meulink.ae (Hub de Links)

### Estratégia:
O meulink.ae deve funcionar como um linktree legítimo, NÃO como
um redirecionamento direto. Deve conter múltiplos links para
demonstrar legitimidade.

### Configuração recomendada:

| Link | Destino | Propósito |
|------|---------|-----------|
| 🌐 Site Oficial | maisquente.com.br | Link principal |
| 📧 Contato | mailto:contato@maisquente.com.br | Legitimidade |
| 📋 Termos de Uso | maisquente.com.br/termos | Compliance |
| 🔒 Privacidade | maisquente.com.br/privacidade | Compliance |

### Por que essa estrutura funciona:
1. **Múltiplos links** = não é redirecionamento automático
2. **Links institucionais** = demonstra empresa real
3. **Sem linguagem explícita** = compliance com Meta
4. **Ação do usuário** = clique consciente (não é cloaking)

### O que NÃO fazer no meulink.ae:
- Não configurar redirecionamento automático (redirect 301/302)
- Não usar apenas um link (parece ponte)
- Não usar imagens explícitas no perfil
- Não usar descrição com termos sexuais

---

## CAMADA 3: maisquente.com.br (Landing Page)

### Papel:
Landing page institucional, legitimadora da marca. É o que o
crawler do Instagram/Meta vai analisar.

### Requisitos técnicos:
- SSL obrigatório (HTTPS)
- Tempo de carregamento < 3s
- Mobile-first
- Meta tags completas (OG, description, canonical)
- robots.txt permitindo indexação
- sitemap.xml

### Estrutura:

```
maisquente.com.br/
├── index.html          ← Homepage institucional (indexável)
├── sobre.html          ← Sobre a empresa (indexável)
├── acesso.html         ← Age gate + redirect (noindex)
├── termos.html         ← Termos de Uso (indexável)
├── privacidade.html    ← Política de Privacidade (indexável)
├── robots.txt
├── sitemap.xml
└── assets/
    ├── favicon.svg
    └── og-image.jpg
```

### Fluxo do usuário:
1. Chega na homepage → vê conteúdo institucional
2. Clica em "Acessar Plataforma" → vai para /acesso
3. Confirma idade → é redirecionado via JavaScript

### Por que isso NÃO é cloaking:
- A homepage não redireciona automaticamente
- O conteúdo é o mesmo para crawlers e humanos
- O redirecionamento requer ação consciente (2 cliques)
- A página /acesso tem noindex (não engana indexadores)
- Existe conteúdo real e substantivo no site

---

## CAMADA 4: hotboys.com.br (Destino Final)

O destino final é acessado APENAS após:
1. Usuário clicar no link do meulink.ae
2. Navegar pelo maisquente.com.br
3. Clicar em "Acessar"
4. Confirmar idade

Isso cria distância suficiente entre Instagram e o destino.

---

## Configuração Técnica

### robots.txt (maisquente.com.br)
```
User-agent: *
Allow: /
Disallow: /acesso

Sitemap: https://maisquente.com.br/sitemap.xml
```

### sitemap.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaschem.org/schemas/sitemap/0.9">
  <url>
    <loc>https://maisquente.com.br/</loc>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://maisquente.com.br/sobre</loc>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://maisquente.com.br/termos</loc>
    <priority>0.5</priority>
  </url>
  <url>
    <loc>https://maisquente.com.br/privacidade</loc>
    <priority>0.5</priority>
  </url>
</urlset>
```

---

## Defesa contra Detecção de Padrão Suspeito

O que torna um funil "suspeito" para o Meta:

| Sinal | Nível de Risco | Nossa Abordagem |
|-------|---------------|-----------------|
| Redirect automático | ALTO | Sem redirect automático |
| Single-page redirect | ALTO | Site com 5 páginas |
| Sem conteúdo real | ALTO | Conteúdo institucional real |
| Termos explícitos na copy | ALTO | Linguagem 100% neutra |
| Sem termos/privacidade | MÉDIO | Ambos presentes |
| Domínio novo sem histórico | MÉDIO | Registrar e aguardar |
| Imagens sugestivas | ALTO | Sem imagens humanas |
| Sem SSL | MÉDIO | HTTPS obrigatório |
| Cloaking (conteúdo diferente) | CRÍTICO | Conteúdo idêntico |
