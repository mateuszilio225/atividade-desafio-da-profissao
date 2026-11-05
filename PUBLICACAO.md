# Publicação do CyberSafe

- Repositório: https://github.com/mateuszilio225/atividade-desafio-da-profissao
- Destino configurado no QR e no link do folder: https://mateuszilio225.github.io/atividade-desafio-da-profissao/
- Página de entrada: `index.html`.
- Folder atualizado: `folder.html` e `folder-cybersafe.pdf`.
- Workflow: `.github/workflows/pages.yml`, com actions oficiais de configuração, upload e implantação no GitHub Pages.

## Resultado observado

**Envio ao GitHub concluído.** O primeiro commit `e17682e7e9021ea687008f56092e8bbd7f9735f3` foi enviado com sucesso para `refs/heads/main` e confirmado por `git ls-remote`. A página pública do repositório respondeu HTTP 200. O usuário autorizou o envio e a implantação.

**Publicação no Pages bloqueada na ativação inicial.** O workflow foi realmente executado e falhou na etapa `Configurar GitHub Pages`: `Resource not accessible by integration`, ao criar o site Pages. O token automático de Actions não tem os privilégios necessários para essa ativação inicial. O Pages ainda não está confirmado como publicado.

Execução verificada: https://github.com/mateuszilio225/atividade-desafio-da-profissao/actions/runs/42131599179

Para desbloquear:

1. O proprietário abre https://github.com/mateuszilio225/atividade-desafio-da-profissao/settings/pages e seleciona **GitHub Actions** em **Build and deployment → Source**.
2. Em **Actions**, abre a execução acima e escolhe **Re-run all jobs**. O workflow existente publica os arquivos; não é necessário recriar o projeto ou gerar outro QR.
3. Depois do sucesso, confirma o acesso a https://mateuszilio225.github.io/atividade-desafio-da-profissao/ em uma janela anônima e no celular.

A preparação local foi concluída: QR do PNG e do PDF lidos com sucesso, link clicável correto, nomes/créditos/logos conferidos e duas páginas A5 sem cortes. A indisponibilidade da API no ambiente e a falta de privilégio do token automático são bloqueios distintos; nenhum deles é atribuído a erro no HTML.

## Restrição de rede observada

O proxy deste ambiente recusou o CONNECT para `api.github.com` e `mateuszilio225.github.io` com HTTP 403. Isso impede consultar a API, ativar/inspecionar o Pages diretamente e verificar o site por HTTPS nesta instância. Não é evidência de senha incorreta ou de HTTP 403 retornado pelo site.

Foram salvas no rascunho da configuração do ambiente as adições mínimas `api.github.com` e `mateuszilio225.github.io`, preservando os presets existentes. O salvamento foi confirmado e retornou `requires_publish: true`. Para aplicar essa mudança, revise e salve nas configurações do ambiente e publique a configuração. Isso é separado da implantação do site no GitHub Pages.

## Acompanhar o GitHub Pages

Veja **Actions → Publicar CyberSafe no GitHub Pages**. O workflow tenta habilitar o Pages automaticamente. Se o GitHub negar essa configuração por privilégios do token de Actions, o proprietário deve selecionar **Settings → Pages → Source → GitHub Actions** e executar novamente o workflow. Depois de concluir, confira a URL de implantação e teste em janela anônima/rede móvel antes de divulgar o folder.

Não há postagem automática em redes sociais nem entrega acadêmica automática.
