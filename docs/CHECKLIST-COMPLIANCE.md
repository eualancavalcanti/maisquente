# Checklist de Compliance — Instagram / Meta

## STATUS GERAL

Use este checklist antes de cada publicação ou alteração no funil.

---

## ✅ O QUE É ACEITÁVEL (Risco Baixo)

- [x] Usar "entretenimento adulto" como categoria
- [x] Dizer "conteúdo para maiores de 18"
- [x] Usar "produções originais" como descrição
- [x] Ter verificação de idade (age gate)
- [x] Redirecionar via clique consciente do usuário
- [x] Ter site com múltiplas páginas (não thin content)
- [x] Ter Termos de Uso e Política de Privacidade
- [x] Usar domínio com SSL (HTTPS)
- [x] Ter página "Sobre" com informações da empresa
- [x] Usar hub de links com múltiplas opções (não redirect direto)
- [x] Usar linguagem genérica: "Acessar Plataforma"
- [x] Usar palavras: "premium", "exclusivo", "original", "bastidores"
- [x] Ter meta tags completas (OG, description, canonical)
- [x] Página de redirecionamento com `noindex`

---

## ❌ O QUE DEVE SER EVITADO (Risco Alto → Bloqueio)

### Na Bio do Instagram:
- [ ] Termos sexuais explícitos
- [ ] Menção direta ao site final (hotboys)
- [ ] Promessas de nudez ou conteúdo sexual
- [ ] Emojis sexuais (🍆🍑🔥 em contexto sexual)
- [ ] Hashtags adultas (#nsfw, #nude, etc.)

### No Feed/Stories do Instagram:
- [ ] Imagens com nudez parcial ou sugestiva
- [ ] Screenshots do site final
- [ ] Thumbnails com conteúdo explícito
- [ ] CTAs como "assine e veja tudo", "conteúdo proibido"
- [ ] Menção de preços de assinatura do destino final

### No meulink.ae:
- [ ] Redirect automático (301/302)
- [ ] Apenas 1 link (parece bridge page)
- [ ] Imagem de perfil explícita
- [ ] Descrição com termos sexuais

### No maisquente.com.br:
- [ ] Imagens com nudez ou sugestão
- [ ] Termos explícitos na copy (nude, sexo, xxx, porn)
- [ ] Redirect automático na homepage
- [ ] Conteúdo diferente para crawlers vs humanos (cloaking)
- [ ] Preços do site final
- [ ] Iframe ou embed do site final
- [ ] Thumbnails de vídeos explícitos
- [ ] Palavras-chave em meta tags que referenciem conteúdo sexual

---

## ⚠️ O QUE PODE DERRUBAR (Gatilhos de Bloqueio)

### Gatilho 1: Cloaking
**O que é:** Mostrar conteúdo diferente para o crawler do Meta
e para o usuário humano.
**Como evitar:** Servir exatamente o mesmo HTML para todos.
**Status atual:** ✅ Sem cloaking — página estática idêntica.

### Gatilho 2: Bridge Page
**O que é:** Página que existe apenas para redirecionar, sem
conteúdo próprio.
**Como evitar:** Ter conteúdo real (5 páginas, copy institucional).
**Status atual:** ✅ Site com conteúdo institucional real.

### Gatilho 3: Conteúdo Explícito no Link de Destino
**O que é:** O crawler do Meta pode seguir links e analisar
a página de destino.
**Como evitar:** O link de redirecionamento está em /acesso
que tem `noindex, nofollow`. O redirect é via JavaScript
(não é um `<a href>` seguível por crawler).
**Status atual:** ✅ Redirect via JS, não seguível.

### Gatilho 4: Denúncias de Usuários
**O que é:** Usuários denunciam o perfil/link.
**Como evitar:** Manter conteúdo do Instagram 100% dentro
das políticas. Mesmo se denunciado, uma revisão manual não
deve encontrar violação no link imediato.
**Status atual:** ✅ Link aponta para meulink.ae → maisquente.com.br
(ambos limpos).

### Gatilho 5: Padrão de Domínio
**O que é:** Meta pode blacklistar domínios inteiros.
**Como evitar:** O domínio maisquente.com.br não contém
conteúdo explícito. Não deve ser confundido com site adulto.
**Status atual:** ✅ Domínio limpo.

### Gatilho 6: Repetição de Padrão
**O que é:** Múltiplas contas usando a mesma estrutura.
**Como evitar:** Usar apenas com a conta principal. Não
replicar o funil em múltiplas contas.
**Status atual:** ⚠️ Garantir uso em conta única.

---

## REVISÃO PRÉ-PUBLICAÇÃO

Antes de publicar qualquer conteúdo no Instagram:

1. [ ] O post contém nudez ou sugestão? → NÃO publique
2. [ ] O texto menciona termos sexuais? → NÃO publique
3. [ ] O CTA promete conteúdo explícito? → REESCREVA
4. [ ] A imagem passaria em um perfil de lifestyle? → OK
5. [ ] O link na bio aponta para meulink.ae? → OK
6. [ ] O meulink.ae tem múltiplos links? → OK
7. [ ] O maisquente.com.br está com SSL? → OK
8. [ ] A página /acesso está com noindex? → OK

---

## MONITORAMENTO CONTÍNUO

### Semanal:
- Verificar se o link na bio continua ativo
- Verificar se o maisquente.com.br carrega corretamente
- Revisar DMs por possíveis avisos do Instagram

### Mensal:
- Verificar Google Search Console (se indexado)
- Verificar se o domínio não está em blacklists
- Revisar políticas atualizadas do Instagram/Meta

### Se receber aviso:
1. NÃO entrar em pânico
2. Verificar qual link/post foi flagged
3. Remover o conteúdo específico (não toda a conta)
4. Apelar com base nos termos (site institucional legítimo)
5. Considerar trocar o meulink.ae se necessário

---

## PALAVRAS SEGURAS vs PROIBIDAS

### ✅ Usar livremente:
- Entretenimento, lifestyle, premium
- Produções originais, bastidores
- Conteúdo exclusivo, membros
- Plataforma, hub, acesso
- Maior de 18, público adulto
- Qualidade profissional

### ❌ Nunca usar:
- Nude, nudez, pelado, sem roupa
- Sexo, sexual, erótico, pornô
- Gostoso, safado, proibido
- Assine e veja, conteúdo quente
- Onlyfans, cam, webcam
- XXX, 18+🔥, NSFW

### ⚠️ Usar com cuidado (contexto importa):
- Hot (no nome da marca, OK como branding)
- Adulto (como classificação etária, não como sinônimo de sexual)
- Exclusivo (pode ser interpretado como paywall de conteúdo adulto)
- Premium (pode ser associado a subscription adulta)
