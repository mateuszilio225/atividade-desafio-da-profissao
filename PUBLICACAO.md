# Publicação do CyberSafe

**Situação atual: publicado no GitHub Pages.**

- Site: https://mateuszilio225.github.io/atividade-desafio-da-profissao/
- Repositório: https://github.com/mateuszilio225/atividade-desafio-da-profissao
- Commit da aplicação implantada: `edf9e8d` — correção do semestre para **2026/2**.
- Execução concluída com **Success**, em 21 segundos: https://github.com/mateuszilio225/atividade-desafio-da-profissao/actions/runs/42132599185
- A etapa de implantação informou o endereço acima e gerou o artefato `github-pages`.
- Página de entrada: `index.html`; folder atualizado: `folder.html` e `folder-cybersafe.pdf`.

## Correções aplicadas

O semestre foi alterado para **2026/2** em cabeçalho, ficha acadêmica, créditos, rodapé, duas faces do folder, PDF e documentos. O PDF foi reexportado; a leitura do QR continua retornando o endereço do próprio projeto.

A execução anterior falhou ao ativar o Pages (`Resource not accessible by integration`), explicando o erro “There isn't a GitHub Pages site here” mostrado pelo usuário. Na nova execução, a publicação foi concluída com sucesso. Não há mais bloqueio de ativação observado na implantação atual.

## Validação e limites

O site e o folder foram conferidos em Chromium local; as cinco larguras não apresentaram overflow. O texto extraído do PDF confirmou quatro identificações com 2026/2 e nenhuma com o semestre antigo. QR e link clicável do PDF apontam para o projeto.

A publicação remota foi confirmada pela página pública de Actions e pelo resultado da etapa de implantação. A tentativa de obter o HTML diretamente pelo domínio `mateuszilio225.github.io` ainda foi bloqueada pelo proxy deste ambiente (CONNECT 403); não se afirma HTTP 200 verificado por esta instância. Esse bloqueio de rede local é distinto do 404 anterior do Pages.

As adições `api.github.com` e `mateuszilio225.github.io` continuam salvas no rascunho da configuração do ambiente; para aplicá-las, é necessário revisar, salvar e publicar essa configuração. Isso é separado da publicação do site, que já foi concluída no GitHub.

O workflow `.github/workflows/pages.yml` mantém a publicação automática a cada push em `main`. Não há build da aplicação ou backend.

Não foi realizada postagem em redes sociais nem entrega acadêmica automática. Testes físicos em celular e impressão continuam sob revisão da dupla.

## Atualização do folder para uma página

O usuário solicitou uma única página, somente frente, com QR visível e chamada mais atrativa. Foram atualizados o HTML, o PDF A5 de **uma página** e o PNG de divulgação. QR, link escrito e botão clicável foram verificados, inclusive com leitura do QR diretamente da única página exportada. O workflow também inclui a imagem PNG no artefato publicado. A execução desta atualização deve ser confirmada após o push; o sucesso anterior citado acima corresponde à versão anterior do folder.
