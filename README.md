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

## Antes de apontar um domínio

Três endereços estão fixos no `<head>` do `index.html` apontando para
`https://gvdesiigner.com.br/conteudo`: o `canonical`, o `og:url` e o `og:image`.
Se o endereço final for outro, trocar os três. O `og:image` precisa ser URL
absoluta, senão o preview do link não aparece.

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
