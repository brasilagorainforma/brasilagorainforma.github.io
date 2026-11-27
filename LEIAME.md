# Site do Brasil Agora Informa

Portal nacional da rede "Informa" (irmão do Ribeirão Informa). Site estático e app instalável (PWA),
grátis no GitHub Pages. Endereço previsto: https://brasilagorainforma.github.io (organização anônima
`brasilagorainforma` no GitHub, ainda a criar).

As notícias ficam em `data/noticias.json` e as artes em `midia/AAAA-MM-DD/`.
Capa, seções, agenda e página de cada matéria são montadas sozinhas a partir desse arquivo.

## Seções e editorias
| Seção | Editorias | Cor |
|---|---|---|
| Brasil | BRASIL, NACIONAL, CIDADES, ESTADOS, SEGURANÇA, CLIMA, TEMPO, URGENTE (e qualquer editoria desconhecida) | #0b2a5b |
| Política | POLÍTICA, GOVERNO FEDERAL, CONGRESSO, JUSTIÇA | #1f4e9c |
| Economia | ECONOMIA, NEGÓCIOS, EMPREGO, CONCURSOS, SEU DINHEIRO | #212529 |
| Serviço | SERVIÇO, UTILIDADE, BENEFÍCIOS | #0f5e57 |
| Saúde | SAÚDE, BEM-ESTAR, VIDA | #0b7285 |
| Esporte | ESPORTE, FUTEBOL, BRASILEIRÃO, SELEÇÃO | #14703a |
| Mundo | MUNDO, INTERNACIONAL | #5f2b8f |
| Tecnologia | TECNOLOGIA, CIÊNCIA, GOLPES | #3b5bdb |
| Cultura | CULTURA, SHOW, MÚSICA, CINEMA, TV, LAZER, EVENTO | #d9480f |

URGENTE aparece em vermelho (#b3122e).

## Rotina (cada notícia)
Da raiz do site:

    python3 scripts/adicionar_noticia.py <legenda.txt> [card.png] --editoria ECONOMIA [--link URL] [--destaque]
        [--foto foto.jpg --credito-foto "Imagem ilustrativa: ..."] [--notificar]

Regra de foto (27/11/2026): toda imagem é OLHADA antes de entrar. Nada amador, com data carimbada
ou marca d'água, com bandeira/uniforme/cenário de outro país, pessoa que possa ser confundida com
o personagem da notícia, ou fora do assunto. Sem foto boa: sem foto (quadro na cor da seção) ou
ilustração neutra com o aviso "Imagem ilustrativa".

Commit sempre com autor anônimo:

    git -c user.name="Brasil Agora Informa" -c user.email="noreply@brasilagorainforma.invalid" commit -am "Notícias de <data>"

## Avisos no celular (OneSignal)
`ONESIGNAL_APP_ID` em `assets/app.js` e a variável `ONESIGNAL_APP_ID` do repositório ficam vazias até
criar o app no OneSignal com o e-mail do portal. A chave `ONESIGNAL_API_KEY` vai só nos segredos do
repositório, nunca no código.

## Redes
Links no topo de `assets/app.js` (objeto REDES). Link vazio = ícone escondido.
As páginas /canal, /whatsapp e /zap apontam para a capa até o canal do WhatsApp existir.
