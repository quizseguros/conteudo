# Landing page · Gestão de conteúdo

Página de destino do link da bio do Instagram, voltada a quem vende produto caro
por grupo fechado. O visitante chega de uma DM sobre gestão de conteúdo, e a página
confirma essa promessa com o resultado da Arkano Club.

Site estático, um arquivo só. Sem build, sem dependência, sem framework.

## Publicar

Qualquer host de estático serve. A raiz do repositório já é a raiz do site.

- **Vercel / Netlify:** importar o repositório, sem comando de build, diretório de saída `.`
- **GitHub Pages:** Settings → Pages → branch `main`, pasta `/ (root)`

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | a página inteira: HTML, CSS e JS |
| `banner-desktop.webp` / `.png` | mockup do herói em telas de 961px pra cima |
| `banner-mobile.webp` / `.png` | mockup do herói em telas estreitas |
| `og-conteudo.png` | preview do link em WhatsApp, Instagram e redes |
| `identidade/` | logo e símbolo |

O WebP é o que praticamente todo mundo baixa; o PNG é reserva para navegador antigo.

## Endereço e preview do link

A página tem dois endereços de propósito:

- **https://gvdesiigner.com.br/conteudo** é o endereço bom. O projeto `gvdesiigner`
  tem um rewrite no `vercel.json` dele que serve este deploy nesse caminho. O código
  e o deploy continuam aqui; lá só passa o roteamento.
- **https://gvdesiigner-conteudo.vercel.app** é o deploy direto, que o rewrite
  consome. Funciona sozinho, mas é espelho.

Por isso o `canonical` e o `og:url` apontam para o domínio próprio, e um script no
`<head>` injeta `noindex, nofollow` quando o host é `.vercel.app`, para o espelho
não competir com o endereço bom no Google. O script decide pelo host que aparece
na barra do visitante, que através do rewrite continua sendo o domínio próprio.

**Os caminhos das imagens são absolutos de propósito.** Em `/conteudo`, sem barra
no final, caminho relativo resolve contra a raiz do domínio e quebra. Absoluto
funciona em `/conteudo`, em `/conteudo/` e no `.vercel.app`, sem redirecionamento.

O `og:image` fica no `.vercel.app` porque precisa responder 200 hoje: se apontar
para um domínio que ainda não resolve, o preview do link no WhatsApp e no
Instagram sai sem imagem.

## O print do dono da Arkano Club

A seção de prova tinha um print da mensagem do Guilherme, dono da Arkano Club,
no grupo de clientes dele. **Está fora desta versão**, esperando a autorização
por escrito dele, porque a imagem traz nome e foto e este repositório é público.

Os três cards da seção de prova (80 relógios, 39 clientes novos, julho) continuam
no ar: o número vem da mensagem dele, o que sai é só a imagem.

Para religar depois da autorização: subir `prova-arkano-grupo.png` na raiz,
tirar a classe `sem-print` da `div.prova-inner` e devolver o bloco `.print-wrap`,
que está preservado no arquivo de origem em
`Eu Gvdesiigner/saidas/site-gvdesiigner/conteudo/index.html`. O CSS do print
(`.print-frame`, `.print-legenda`, halo lateral) já está aqui, não precisa mexer.

## De onde vêm os números

Todo número da página sai de `Guilherme Franco ARKANO CLUB/arkano-dados.md`,
levantado da API oficial do Instagram em 13/09/2026, com exceção de vendas e
clientes novos, que são o que o próprio dono anunciou no grupo. Nada foi estimado,
arredondado para cima ou deduzido. Ao editar, conferir contra esse arquivo em vez
de reescrever de memória.

## Origem

Mantido em `Eu Gvdesiigner/saidas/site-gvdesiigner/conteudo/` no workspace do
MazyOS. Este repositório é a cópia de publicação: os caminhos dos arquivos foram
trocados de `../` para a raiz.
