# Orçamento Pessoal — PWA

App de orçamento (proventos × despesas) instalável no celular, com painel,
exportação Excel/PDF e funcionamento offline. Uso individual, dados salvos
no próprio aparelho (`localStorage`).

## Arquivos

- `index.html` — o app
- `manifest.webmanifest` — metadados do PWA (nome, ícones, cores)
- `sw.js` — service worker (cache/offline)
- `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png`, `favicon-64.png` — ícones

> Todos os arquivos precisam ficar **na mesma pasta**.

## Publicar no GitHub Pages

1. Crie um repositório (ex.: `orcamento`) na sua conta `patrick-bjp`.
2. Suba todos os arquivos desta pasta na **raiz** do repositório.
3. No repositório: **Settings → Pages → Source: Deploy from a branch**,
   branch `main`, pasta `/ (root)` → **Save**.
4. Em ~1 min o app estará em:
   `https://patrick-bjp.github.io/orcamento/`

> O HTTPS do GitHub Pages é obrigatório para o PWA funcionar (service worker + instalação).

## Instalar no Android (Chrome)

1. Abra o link acima no Chrome.
2. Menu (⋮) → **Adicionar à tela inicial** / **Instalar app**.
3. O ícone aparece na home. Ao abrir, roda em tela cheia, sem barra do navegador.
4. Repita no celular da Jessica — cada aparelho terá seus próprios dados
   (a sincronização entre vocês é a próxima etapa: Cloudflare Worker + KV).

## Observações

- **Onde os dados ficam:** no navegador de cada aparelho (`localStorage`).
  Não sincroniza entre celulares ainda e some se você limpar os dados do site.
- **Offline:** depois da primeira abertura online, o app abre sem internet.
  As exportações Excel/PDF dependem de bibliotecas de CDN — ficam disponíveis
  offline após a primeira visita, quando o service worker as cacheia.
- **Meses:** julho/2026 a dezembro/2027.
