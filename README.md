# 🏐 RALLY! — O Card Game de Vôlei

Protótipo digital jogável do **Rally!**, um card game de duelo com temática de vôlei para 2 jogadores. Cada carta é um fundamento do esporte — Manchete, Levantamento e Corte — e a ordem dos toques importa, como na quadra.

**Jogue agora:** depois de publicar no GitHub Pages, o jogo fica disponível em `https://SEU-USUARIO.github.io/NOME-DO-REPO/`

## Idiomas

O site é bilíngue (**português / inglês**). O idioma é detectado pelo navegador e pode ser trocado a qualquer momento pelo botão **EN/PT** no topo — inclusive no meio de uma partida online, e cada jogador vê o jogo no próprio idioma (nomes das cartas, narração, tudo). Também dá para forçar via URL: `?lang=en` ou `?lang=pt`.

## Modos de jogo

- **🎮 Local** — 2 jogadores no mesmo aparelho (as duas mãos ficam visíveis; ideal para playtest presencial).
- **🌐 Online** — um jogador cria a sala e envia o link/código; o outro entra. Cada jogador vê apenas a própria mão. A conexão é direta entre os navegadores (WebRTC via [PeerJS](https://peerjs.com/)), sem servidor próprio e sem custo.

> No modo online, quem cria a sala é o **Jogador 1** e saca o primeiro rally. O navegador do criador da sala é o "árbitro" (roda as regras); se ele fechar a aba, a partida termina.

## Como publicar no GitHub Pages (grátis)

1. Crie um repositório novo no GitHub (ex.: `rally-card-game`), público.
2. Envie os arquivos deste projeto para o repositório — pela interface web (*Add file → Upload files*) ou por git:
   ```bash
   git init
   git add .
   git commit -m "Rally! v0.4"
   git branch -M main
   git remote add origin https://github.com/SEU-USUARIO/rally-card-game.git
   git push -u origin main
   ```
3. No repositório, vá em **Settings → Pages**.
4. Em *Build and deployment*, escolha **Deploy from a branch**, branch **main**, pasta **/ (root)** e salve.
5. Em 1–2 minutos o jogo estará no ar em `https://SEU-USUARIO.github.io/rally-card-game/`.

## Estrutura

```
index.html   → o jogo completo (motor + interface + rede) em um único arquivo
docs/        → manual de regras (PT/EN) e sell sheets (PT/EN) em PDF
```

## Regras em 30 segundos

Vença fazendo **3 pontos**. O rally começa com um **Saque** (jogado junto de 1 carta, cujo Ataque define o poder; poder ≥ 4 vira saque-corte). O defensor precisa de uma carta com **Defesa ≥ poder do ataque** e então arma a resposta na ordem do vôlei: **Manchete → Levantamento → Corte**, somando os ataques. Não conseguiu defender? Ponto do adversário. O manual completo está em [`docs/RALLY-manual-PT.pdf`](docs/RALLY-manual-PT.pdf) ([English version](docs/RALLY-rulebook-EN.pdf)).

## Roadmap técnico

- [ ] Servidor autoritativo (Node + WebSocket) para salas persistentes e reconexão — o motor do jogo já é isolado da camada de rede (`engine*` vs `ui*`/PeerJS), então a migração troca apenas o transporte.
- [ ] Espectadores e revanche automática.
- [ ] Modo de duplas (4 jogadores).

---

Design: **Herbert Parasio** — herbert.parasio@gmail.com
