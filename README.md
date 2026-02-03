# Landing Page IPTV - Vue 3

Landing page profissional para serviços de IPTV com mais de 1500 canais.

## 🚀 Tecnologias

- Vue 3
- Vue Router
- Tailwind CSS
- Vite
- Express (para produção)

## 📦 Instalação

```bash
npm install
```

## 🛠️ Desenvolvimento

```bash
npm run dev
```

Acesse: http://localhost:3000

## 🏗️ Build

```bash
npm run build
```

## 🌐 Deploy no Heroku

### Configuração Automática

O projeto já está configurado com:
- ✅ `Procfile` - Define o comando de inicialização
- ✅ `server.js` - Servidor Express para servir arquivos estáticos
- ✅ Scripts npm apropriados

### Passos para Deploy:

1. **Crie uma conta no Heroku** (se ainda não tiver)

2. **Instale o Heroku CLI**:
```bash
brew tap heroku/brew && brew install heroku
```

3. **Faça login no Heroku**:
```bash
heroku login
```

4. **Crie uma aplicação no Heroku**:
```bash
heroku create nome-da-sua-app
```

5. **Configure as variáveis de ambiente (se necessário)**:
```bash
heroku config:set NODE_ENV=production
```

6. **Faça o deploy**:
```bash
git push heroku main
```

7. **Abra sua aplicação**:
```bash
heroku open
```

### Deploy via Dashboard do Heroku

Se você preferir usar a interface web:

1. Acesse https://dashboard.heroku.com
2. Crie um novo app
3. Na aba "Deploy", conecte ao seu repositório GitHub
4. Ative "Automatic Deploys" ou faça deploy manual
5. Certifique-se de que o buildpack está configurado como:
   - `heroku/nodejs`

### Buildpacks

O Heroku detectará automaticamente que é um projeto Node.js. Se necessário, configure manualmente:

```bash
heroku buildpacks:set heroku/nodejs
```

### Logs

Para ver os logs da aplicação:

```bash
heroku logs --tail
```

## 📁 Estrutura do Projeto

```
vue-iptv/
├── public/              # Arquivos públicos
├── src/
│   ├── components/      # Componentes Vue
│   │   ├── Navbar.vue
│   │   ├── HeroSection.vue
│   │   ├── BenefitsSection.vue
│   │   ├── UrgencySection.vue
│   │   ├── PricingSection.vue
│   │   ├── FaqSection.vue
│   │   └── Footer.vue
│   ├── router/          # Configuração de rotas
│   ├── views/           # Páginas
│   │   ├── Home.vue
│   │   ├── ThankYou.vue
│   │   └── SoldOut.vue
│   ├── App.vue
│   ├── main.js
│   └── style.css
├── Procfile            # Configuração Heroku
├── server.js           # Servidor Express
├── package.json
├── vite.config.js
└── tailwind.config.js
```

## 🎨 Personalização

### Cores e Estilo

Edite o arquivo `tailwind.config.js` para customizar as cores do tema.

### Conteúdo

Os componentes estão em `src/components/` e podem ser editados individualmente:
- FAQ: `FaqSection.vue`
- Preços: `PricingSection.vue`
- Benefícios: `BenefitsSection.vue`

### Rotas

As rotas estão configuradas em `src/router/index.js`:
- `/` - Página inicial
- `/obrigado` - Página de confirmação
- `/esgotado` - Página de promoção esgotada

## 📝 Licença

Este projeto é privado.

## 🤝 Contato

Para mais informações, entre em contato através das redes sociais.
