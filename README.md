# 🚀 LebreVet — Deploy no Vercel (Passo a Passo)

Landing page de conversão para captar tutores via Google Ads → WhatsApp.

---

## ⚡ Deploy RÁPIDO (3 minutos)

### Opção A — Deploy pela interface web (mais fácil)

1. Acessa **https://vercel.com/signup** e cria conta (login com GitHub ou email)
2. Clica em **"Add New..." → "Project"**
3. Arrasta a pasta inteira deste projeto (`lebrevet-vercel`) para a tela
4. Clica em **"Deploy"**
5. Pronto — você recebe uma URL tipo `lebrevet-landing-xxx.vercel.app`

### Opção B — Deploy via terminal (Vercel CLI)

```bash
# 1. Instala o Vercel CLI globalmente (só precisa fazer uma vez)
npm install -g vercel

# 2. Entra na pasta do projeto
cd lebrevet-vercel

# 3. Primeiro login (abre o navegador)
vercel login

# 4. Deploy de teste
vercel

# 5. Deploy de produção
vercel --prod
```

---

## 🌐 Conectar Domínio Próprio (ex: lebrevet.com.br)

Após o deploy, na dashboard do Vercel:

1. Entra no seu projeto
2. **Settings → Domains**
3. Adiciona `lebrevet.com.br` (ou o domínio que você tem)
4. O Vercel te dá os registros **DNS A** e **CNAME** para colocar no seu registrador (Registro.br, GoDaddy, etc.)
5. Aguarda propagação (15 min a 2h)

---

## 📊 Checklist Pós-Deploy (CRÍTICO)

Antes de colocar no Google Ads, valida:

- [ ] LP abre corretamente no celular (teste em Android e iPhone se possível)
- [ ] Todos os botões "WhatsApp" abrem o WhatsApp com a mensagem certa
- [ ] Botão de telefone (no header mobile) abre o dialer corretamente
- [ ] Passa o teste no **PageSpeed Insights**: https://pagespeed.web.dev/
  - Meta mobile: **score acima de 85**
  - Meta desktop: **score acima de 90**
- [ ] O Schema.org aparece no **Rich Results Test**: https://search.google.com/test/rich-results

---

## 📁 Estrutura do Projeto

```
lebrevet-vercel/
├── index.html          # Landing page principal
├── vercel.json         # Config de produção (cache, segurança)
├── package.json        # Metadata do projeto
├── .gitignore          # Arquivos ignorados
├── README.md           # Este arquivo
└── images/
    ├── hero-cao.jpg    # 78KB — Hero (lazy=eager)
    ├── gata.jpg        # 68KB — Seção felinos
    ├── pastor.jpg      # 69KB — Seção cães grandes
    ├── pitbull.jpg     # 69KB — Seção serviços
    └── dr-lebre.jpg    # 19KB — Mascote footer
```

**Total: ~310KB de imagens + 30KB HTML = ~340KB total**
Carrega em <2s no 4G de Marília.

---

## 🔧 O que o `vercel.json` faz por você

- **Cache de 1 ano** nas imagens (visitor repetido carrega quase instantâneo)
- **Cache desabilitado no HTML** (mudanças aparecem imediatamente)
- **Headers de segurança** (X-Frame-Options, Content-Type, Referrer-Policy)
- **Permissions-Policy** restritiva (câmera/mic/geo desabilitados)
- **URLs limpas** (sem `.html` no final)

---

## 📞 Contato

- WhatsApp: **(14) 99606-8010**
- Cidade: **Marília-SP**
- Atendimento domiciliar premium
