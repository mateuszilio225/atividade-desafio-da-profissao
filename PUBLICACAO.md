# Publicação do CyberSafe

**Situação atual: publicado no GitHub Pages.**

- Site: https://mateuszilio225.github.io/atividade-desafio-da-profissao/
- Repositório: https://github.com/mateuszilio225/atividade-desafio-da-profissao
- Commit da aplicação implantada: `bb92062` — folder de **uma página**, com QR na frente, PDF e PNG atualizados; semestre **2026/2** preservado.
- Execução concluída com **Success**, em 19 segundos: https://github.com/mateuszilio225/atividade-desafio-da-profissao/actions/runs/42134144481
- A etapa de implantação informou o endereço acima e gerou o artefato `github-pages`.
- Página de entrada: `index.html`; folder atualizado: `folder.html`, `folder-cybersafe.pdf` e `folder-cybersafe.png`.

## Correções aplicadas

O semestre foi alterado para **2026/2** em cabeçalho, ficha acadêmica, créditos, rodapé, única face do folder, PDF e documentos. O PDF foi reexportado; a leitura do QR continua retornando o endereço do próprio projeto.

A execução anterior falhou ao ativar o Pages (`Resource not accessible by integration`), explicando o erro “There isn't a GitHub Pages site here” mostrado pelo usuário. Na nova execução, a publicação foi concluída com sucesso. Não há mais bloqueio de ativação observado na implantação atual.

## Validação e limites

O site e o folder foram conferidos em Chromium local; as cinco larguras não apresentaram overflow. O PDF atualizado foi confirmado com exatamente uma página A5, nomes e identificação acadêmica completos, semestre 2026/2 e QR decodificado na própria página exportada. QR e link clicável do PDF apontam para o projeto.

A publicação remota foi confirmada pela página pública de Actions e pelo resultado da etapa de implantação. A tentativa de obter o HTML diretamente pelo domínio `mateuszilio225.github.io` ainda foi bloqueada pelo proxy deste ambiente (CONNECT 403); não se afirma HTTP 200 verificado por esta instância. Esse bloqueio de rede local é distinto do 404 anterior do Pages.

As adições `api.github.com` e `mateuszilio225.github.io` continuam salvas no rascunho da configuração do ambiente; para aplicá-las, é necessário revisar, salvar e publicar essa configuração. Isso é separado da publicação do site, que já foi concluída no GitHub.

O workflow `.github/workflows/pages.yml` mantém a publicação automática a cada push em `main`. Não há build da aplicação ou backend.

Não foi realizada postagem em redes sociais nem entrega acadêmica automática. Testes físicos em celular e impressão continuam sob revisão da dupla.

## Atualização do folder para uma página

O usuário solicitou uma única página, somente frente, com QR visível e chamada mais atrativa. Foram atualizados o HTML, o PDF A5 de **uma página** e o PNG de divulgação. QR, link escrito e botão clicável foram verificados, inclusive com leitura do QR diretamente da única página exportada. O workflow também inclui a imagem PNG no artefato publicado. A atualização foi publicada com sucesso pela execução 42134144481, em 19 segundos. A etapa de implantação confirmou a URL pública do projeto e gerou o artefato com HTML, PDF e PNG atualizados.
