

## Criar uma Landing Page para Venda de IPTV

Você é um assistente especialista em criação de landing pages impactantes, com foco em UX/UI, copywriting e marketing digital.

### Objetivo

Crie uma landing page profissional e altamente persuasiva para a venda de serviços de IPTV, destacando acesso a canais de TV, filmes, séries e esportes ao vivo, com suporte de qualidade e entrega imediata. A página deve ser visualmente impactante, transmitir confiança e gerar desejo imediato de contratação.

### Estilo

Para o estilo visual, utilize cores escuras com toques vibrantes, criando um ambiente moderno e tecnológico. A estética deve ser limpa, responsiva, com animações sutis e de alto impacto, transmitindo praticidade, entretenimento e exclusividade.

### Tom

Persuasivo, direto e envolvente, transmitindo a emoção de ter acesso ilimitado ao melhor conteúdo de TV, filmes e esportes, com praticidade e economia.

### Público-alvo

Pessoas que buscam entretenimento de qualidade, acesso a canais exclusivos, filmes, séries, esportes ao vivo, economia em relação à TV tradicional, praticidade e suporte rápido, além de flexibilidade para assistir em qualquer dispositivo.

### Estrutura sugerida


1. Menu de navegação fixo no topo com rolagem suave, contendo links para: Sobre o Serviço, Benefícios, FAQ e Assine Agora.
2. Seção principal (hero): destaque do serviço de IPTV com uma imagem de TV moderna ou dispositivos, slogan chamativo como "Tenha todos os canais, filmes e esportes ao vivo na sua casa" e botão de CTA “Assine Agora”.
3. Seção de detalhes: benefícios do IPTV (acesso imediato, variedade de canais, filmes e séries, esportes ao vivo, suporte rápido), diferenciais do serviço, exemplos de canais e conteúdos disponíveis, lista de dispositivos compatíveis (Smart TV, celular, computador, TV Box, etc.).
4. Seção de exclusividade/urgência: destaque de promoções limitadas, como “Assine hoje e ganhe teste grátis!” ou “Vagas limitadas para o plano promocional”, com chamada de ação para gerar urgência.
5. FAQ com respostas curtas para dúvidas comuns (como funciona o IPTV, formas de pagamento, cancelamento, dispositivos suportados, estabilidade do serviço). Use respostas genéricas para serem alteradas depois.
6. Seção de contratação: botão de destaque com preço (ex: R$ 29,90/mês), opções de pagamento (cartão de crédito, débito, Pix) e garantia de satisfação.
7. Rodapé com links para redes sociais do serviço de IPTV, como Instagram, Facebook e Telegram.
8. Widget flutuante do WhatsApp no canto inferior direito, sempre visível, redirecionando para o WhatsApp Web com número configurável conforme o nicho/cliente.
9. Página extra na rota "/obrigado" informando que a assinatura foi recebida e que o cliente receberá um e-mail de confirmação.
10. Página extra na rota "/esgotado" para redirecionar quando uma promoção específica já tiver esgotado.


Requisitos de design:

1. Design responsivo para todos os dispositivos.
2. Animações sutis para gerar engajamento (hover em botões, fade-in das imagens).
3. Tipografia profissional, legível e moderna.
4. Botões CTA bem destacados e sempre visíveis em momentos estratégicos.
5. Layout otimizado para alta taxa de conversão, com foco em destacar benefícios, variedade de conteúdo e urgência.


## Configuração Técnica (Vue 3 + Vite)


### Estrutura de Arquivos Essenciais

```
projeto/
├── src/
│   ├── components/      # Componentes reutilizáveis da landing page
│   ├── router/          # Vue Router para navegação
│   ├── views/           # Páginas principais (Home, ThankYou, SoldOut)
│   ├── App.vue          # Componente raiz
│   ├── main.js          # Entry point
│   └── style.css        # Estilos globais com Tailwind
├── public/              # Assets estáticos (ex: logos, banners de canais, etc.)
├── server.js            # Servidor Express para produção
├── Procfile             # Configuração Heroku
├── vite.config.js       # Configuração Vite
├── tailwind.config.js   # Configuração Tailwind
└── package.json         # Dependências e scripts
```


### Dependências Necessárias

**Produção:**
- `vue`: ^3.4.15
- `vue-router`: ^4.2.5
- `express`: ^4.18.2 (para servir em produção)

**Desenvolvimento:**
- `@vitejs/plugin-vue`: ^5.0.3
- `vite`: ^5.0.11
- `tailwindcss`: ^3.4.1
- `autoprefixer`: ^10.4.17
- `postcss`: ^8.4.33


### Scripts npm Essenciais

```json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview",
  "start": "node server.js"
}
```


### Configuração para Deploy no Heroku

**1. Procfile** (na raiz do projeto):
```
web: node server.js
```

**2. server.js** (servidor Express para produção):
```javascript
import express from 'express';
import { fileURLToPath } from 'url';
import { dirname, join } from 'path';

const __filename = fileURLToPath(import.meta.url);
const __dirname = dirname(__filename);

const app = express();
const PORT = process.env.PORT || 3000;

// Servir arquivos estáticos da pasta dist
app.use(express.static(join(__dirname, 'dist')));

// Redirecionar todas as rotas para o index.html (SPA)
app.get('*', (req, res) => {
  res.sendFile(join(__dirname, 'dist', 'index.html'));
});

app.listen(PORT, () => {
  console.log(`🚀 Servidor rodando na porta ${PORT}`);
});
```

**3. vite.config.js** (configuração de build):
```javascript
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

export default defineConfig({
  plugins: [vue()],
  server: {
    port: 3000
  },
  build: {
    outDir: 'dist',
    assetsDir: 'assets',
    emptyOutDir: true
  }
})
```

**4. package.json** (deve incluir `"type": "module"`):
```json
{
  "type": "module",
  "scripts": {
    "start": "node server.js"
  }
}
```


### Configuração no Dashboard Heroku

1. **Buildpack**: Use `heroku/nodejs` (detectado automaticamente)
2. **Branch**: `main` ou sua branch de deploy
3. **Caminho de Build**: `/` (deixar vazio se o projeto está na raiz)
4. **Auto Deploy**: Ative para deploy automático ao fazer push


### Processo de Deploy

O Heroku executará automaticamente:
1. `npm install` - Instala dependências
2. `npm run build` - Cria a pasta `dist` com arquivos otimizados
3. `npm start` - Inicia o servidor Express na porta definida pelo Heroku


### Comandos Úteis

```bash
# Desenvolvimento local
npm run dev

# Build para produção
npm run build

# Testar build localmente
npm start

# Deploy via Git
git push heroku main

# Ver logs do Heroku
heroku logs --tail
```


### Checklist de Deploy

- [ ] Criar `Procfile` com `web: node server.js`
- [ ] Criar `server.js` com Express
- [ ] Adicionar `express` nas dependências do package.json
- [ ] Adicionar script `"start": "node server.js"` no package.json
- [ ] Configurar `"type": "module"` no package.json
- [ ] Configurar `build` no vite.config.js
- [ ] Fazer commit de todas as alterações
- [ ] Conectar repositório ao Heroku
- [ ] Fazer push/deploy


### Observações Importantes

- O servidor Express é necessário porque o Heroku precisa de um processo web ativo
- A pasta `dist` é gerada automaticamente durante o build e não deve ser commitada
- O `.gitignore` deve incluir `dist`, `node_modules` e arquivos de log
- Certifique-se de que `"type": "module"` está no package.json para usar ES modules
- O Express redireciona todas as rotas para o index.html, permitindo que o Vue Router funcione corretamente


## Suporte e créditos

- Conceito e demonstração: [Nome do serviço de IPTV]
- Ferramenta utilizada: [Plataforma de hospedagem]
- Vídeo da criação: [Link para vídeo, se disponível]
- Produção: [URL do serviço de IPTV]
