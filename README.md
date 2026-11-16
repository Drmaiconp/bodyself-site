# Site bodyself — Brasil + EUA

Site estático, pronto para a Vercel. Um único endereço mostra:

- **Quem acessa do Brasil** → português, preços em R$ (`/br`)
- **Quem acessa de qualquer outro país** → inglês, preços em US$ (`/us`)

A detecção é feita pela Vercel, pelo país do IP (cabeçalho `x-vercel-ip-country`).
Se a pessoa clicar em **BR · R$** ou **US · US$** no topo, a escolha fica salva no navegador
(cookie `bs_region`) e vale para as próximas visitas.

## Arquivos

| Arquivo | O que é |
|---|---|
| `br.html` | Página em português |
| `us.html` | Página em inglês |
| `styles.css` | Visual do site (cores, fontes, layout) |
| `logo.svg`, `favicon.svg` | Logo e ícone da aba |
| `vercel.json` | Regras de detecção de país |

## Publicar (cerca de 10 minutos)

1. **GitHub** — crie um repositório novo (ex.: `Drmaiconp/bodyself-site`) e envie todos estes arquivos.
   Pelo site do GitHub: *Add file › Upload files* → arraste o conteúdo desta pasta → *Commit*.
2. **Vercel** — em vercel.com: *Add New › Project* → escolha o repositório `bodyself-site`
   → em *Framework Preset* deixe **Other** → *Deploy*. Não precisa de comando de build.
3. **Domínio** — no projeto da Vercel: *Settings › Domains* → adicione o domínio (ex.: `bodyself.us`)
   e siga as instruções de DNS que a Vercel mostrar no registrador do domínio.
4. **Domínio já configurado nas páginas:** bodyself.us (links canonical e alternate).

Toda vez que um arquivo for alterado no GitHub, a Vercel publica a nova versão sozinha.

## Testar

- `seudominio/br` → sempre a versão Brasil
- `seudominio/us` → sempre a versão EUA
- `seudominio/` → automática pelo país (para testar a outra versão, use VPN ou os botões BR/US)

## Preços e contato atuais

- Brasil: R$ 52/mês + anel R$ 310 (pagamento único) — equivalente a US$ 10 + US$ 60
- EUA: $10/mês + anel $60 (pagamento único)
- WhatsApp/telefone: +1 (689) 260-7444 · E-mail: bodyself@comercial.us

Para mudar textos ou preços, edite `br.html` e `us.html` (ou peça ao Claude para gerar de novo).

## Próximo passo: cobrança

Os botões "Assinar agora" / "Join now" levam hoje ao contato. Para vender direto pelo site,
crie no Stripe dois **Payment Links** (um em BRL, outro em USD), cada um com o anel como item
único + a mensalidade recorrente, e troque o link dos botões em cada página.
