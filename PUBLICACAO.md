# Publicação do CyberSafe

- Repositório: https://github.com/mateuszilio225/atividade-desafio-da-profissao
- Destino configurado no QR e no link do folder: https://mateuszilio225.github.io/atividade-desafio-da-profissao/
- Página de entrada: `index.html`.
- Folder atualizado: `folder.html` e `folder-cybersafe.pdf`.
- Workflow: `.github/workflows/pages.yml`, com actions oficiais de configuração, upload e implantação no GitHub Pages.

O usuário autorizou o envio ao repositório e a publicação no Pages. A preparação local foi concluída, incluindo a leitura do QR diretamente do PDF e a presença do link clicável correto. A conclusão do envio e da implantação deve ser registrada abaixo após observar o resultado real.

## Restrição de rede observada

O proxy deste ambiente recusou o CONNECT para `api.github.com` e `mateuszilio225.github.io` com HTTP 403. Isso impede consultar a API, ativar/inspecionar o Pages diretamente e verificar o site por HTTPS nesta instância. Não é evidência de senha incorreta ou de HTTP 403 retornado pelo site.

Foram salvas no rascunho da configuração do ambiente as adições mínimas `api.github.com` e `mateuszilio225.github.io`, preservando os presets existentes. O salvamento foi confirmado e retornou `requires_publish: true`. Para aplicar essa mudança, revise e salve nas configurações do ambiente e publique a configuração. Isso é separado da implantação do site no GitHub Pages.

## Acompanhar o GitHub Pages

Veja **Actions → Publicar CyberSafe no GitHub Pages**. O workflow tenta habilitar o Pages automaticamente. Se o GitHub negar essa configuração por privilégios do token de Actions, o proprietário deve selecionar **Settings → Pages → Source → GitHub Actions** e executar novamente o workflow. Depois de concluir, confira a URL de implantação e teste em janela anônima/rede móvel antes de divulgar o folder.

Não há postagem automática em redes sociais nem entrega acadêmica automática.
