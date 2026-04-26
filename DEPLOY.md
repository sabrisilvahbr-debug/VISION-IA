# 🚀 AlphaVision AI — Guia de Publicação no Vercel

## ✅ Pré-requisitos (tudo gratuito)

1. Conta no **GitHub** → https://github.com
2. Conta no **Vercel** → https://vercel.com (entre com sua conta GitHub)
3. **Chave da Google Gemini API** → https://aistudio.google.com/app/apikey

---

## 🔑 PASSO 1 — Obter a Chave do Google Gemini (GRÁTIS)

1. Acesse: https://aistudio.google.com/app/apikey
2. Faça login com sua conta Google
3. Clique em **"Create API Key"**
4. Copie a chave gerada (começa com `AIza...`)
5. Guarde em lugar seguro — você vai precisar no Passo 4

---

## 📁 PASSO 2 — Subir o código no GitHub

### Opção A — Via GitHub.com (sem instalar nada)

1. Acesse https://github.com e faça login
2. Clique em **"New repository"** (botão verde)
3. Nome: `alphavision-ai` · Deixe **Public** · Clique **"Create repository"**
4. Na página do repositório vazio, clique em **"uploading an existing file"**
5. **Extraia o ZIP** do AlphaVision no seu computador
6. Arraste **todos os arquivos e pastas** para a área de upload do GitHub
7. Clique em **"Commit changes"**

### Opção B — Via terminal (se tiver Git instalado)

```bash
# Extraia o ZIP, entre na pasta e execute:
cd alphavision-ai
git init
git add .
git commit -m "AlphaVision AI - initial commit"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/alphavision-ai.git
git push -u origin main
```

---

## 🌐 PASSO 3 — Importar no Vercel

1. Acesse https://vercel.com e faça login com GitHub
2. Clique em **"Add New Project"** (botão escuro no topo)
3. Encontre seu repositório `alphavision-ai` e clique em **"Import"**
4. Em **"Framework Preset"** selecione: **Next.js** (deve detectar automaticamente)
5. **NÃO clique em Deploy ainda** — vá para o Passo 4 primeiro!

---

## 🔐 PASSO 4 — Configurar as Variáveis de Ambiente

Ainda na tela de configuração do Vercel, expanda **"Environment Variables"** e adicione:

| Nome | Valor |
|------|-------|
| `GOOGLE_GEMINI_API_KEY` | `AIza...` (sua chave do Passo 1) |
| `NEXT_PUBLIC_KIWIFY_URL` | `https://pay.kiwify.com.br/8dq9075` |

Clique em **"Add"** após cada variável.

---

## 🏁 PASSO 5 — Deploy!

1. Clique em **"Deploy"**
2. Aguarde 2-3 minutos enquanto o Vercel faz o build
3. Quando aparecer o confete 🎉, seu app está no ar!
4. Você receberá uma URL como: `https://alphavision-ai.vercel.app`

---

## 🔄 Atualizações futuras

Sempre que você fizer mudanças no código:
- Suba os arquivos novamente no GitHub
- O Vercel faz o redeploy **automaticamente** em menos de 1 minuto

---

## 🐛 Problemas comuns

| Problema | Solução |
|----------|---------|
| Build falha com erro de TypeScript | Verifique se todos os arquivos foram enviados |
| "API Key not configured" no app | Confirme a variável `GOOGLE_GEMINI_API_KEY` no Vercel |
| Análise retorna erro | Verifique se a chave Gemini está ativa em aistudio.google.com |
| Página em branco | Abra o console do navegador (F12) e veja o erro |

---

## 💡 Dicas pós-publicação

- **Domínio próprio**: No painel do Vercel → Settings → Domains → adicione seu domínio
- **Analytics**: O Vercel tem analytics grátis em Settings → Analytics
- **Logs**: Em caso de erro na API, veja em Vercel → Functions → Logs

---

## 📞 Estrutura do projeto

```
alphavision-ai/
├── pages/
│   ├── _app.tsx          # App wrapper + metadados SEO
│   ├── index.tsx         # Roteamento entre telas
│   └── api/
│       └── analyze.ts    # 🧠 API de análise com Gemini
├── components/
│   ├── Landing.tsx       # Landing page completa
│   ├── Auth.tsx          # Tela de login/cadastro
│   ├── Dashboard.tsx     # Dashboard principal
│   ├── AnalyzeTab.tsx    # Upload + análise
│   ├── HistoryTab.tsx    # Histórico de análises
│   ├── AnalysisResultCard.tsx  # Card de resultado
│   ├── Ticker.tsx        # Barra de preços animada
│   └── UpgradeModal.tsx  # Modal de upgrade PRO
├── lib/
│   └── types.ts          # TypeScript types
├── styles/
│   └── globals.css       # CSS global + animações
├── .env.example          # Template de variáveis
├── vercel.json           # Config do Vercel
└── DEPLOY.md             # Este arquivo
```

---

**Qualquer dúvida, o suporte está aqui! 🚀**
