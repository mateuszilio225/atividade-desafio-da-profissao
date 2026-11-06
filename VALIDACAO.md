# Validação — CyberSafe

## Folder atual: uma única página/face

O usuário solicitou a substituição do folder de duas faces por **uma página, somente frente, com QR na mesma face**. Essa é a versão vigente de `folder.html`, `folder-cybersafe.pdf` e `folder-cybersafe.png`.

Verificações executadas em Chromium com Playwright:

| Verificação | Resultado observado |
|---|---|
| Estrutura | Um único bloco de página e um H1. Logos da ATITUS e do curso presentes na mesma face. |
| Conteúdo obrigatório | As três dicas completas, instituição, curso, disciplina, docente, Mateus Zilio e Yuri Antonini e semestre **2026/2** estão presentes. A identificação acadêmica completa foi mantida. |
| QR na frente | Um único QR na única página, no bloco de chamada anterior às dicas e aos créditos. Sem placeholder ou verso. |
| Destinos | QR e URL escrita apontam para `https://mateuszilio225.github.io/atividade-desafio-da-profissao/`. Botão “QUERO FAZER O DESAFIO” aponta para `#desafio` da mesma página. CERT.br aparece apenas como fonte externa identificada. |
| PDF | `pdfinfo` confirmou **Pages: 1**, tamanho A5 (420 × 594,96 pontos). Altura de conteúdo não excedeu a página. Extração de texto confirmou nomes, semestre e identificação sem cortes. |
| Leitura do QR | ZXing-C++ decodificou o QR da primeira e única página do PDF renderizada em PNG, retornando exatamente a URL do projeto. Zona livre de quatro módulos preservada; QR com 35 mm no PDF. |
| Links no PDF | `pdfinfo -url` confirmou anotações clicáveis para o guia, o desafio e a referência CERT.br. |
| Imagem de divulgação | Gerada da única página do PDF em 300 dpi, **1750 × 2479 px**, sem marcas de corte ou área de navegação do navegador. PNG não tem links clicáveis; use a URL na legenda ao divulgar. |
| Responsividade | 320, 375, 768, 1024 e 1440 px: sem overflow horizontal; QR visível e dentro da largura da tela. |
| Teclado | Foco em sequência entre QR, botão e URL escrita; foco visível. |
| Acessibilidade automática | axe-core 4.10.3 em 375 e 1440 px: **25 regras aprovadas, zero violações automáticas**, uma regra inconclusiva em cada largura. Sem declaração de conformidade integral com WCAG. |
| JavaScript | Nenhuma exceção durante a validação do folder; ele não depende de JavaScript para funcionar. |
| Revisão visual | PDF de uma página inspecionado: chamada principal, QR, botão, dicas e créditos na mesma face. Sem alegações de proteção absoluta, pesquisas ou resultados de aprendizagem inventados. |

Ferramentas de QA e geração usadas no ambiente não são dependências da aplicação. O QR foi preservado durante a mudança de composição; o destino continua sendo a página do projeto.

## Landing page

As funcionalidades principais foram verificadas nas etapas anteriores, sem alteração de sua lógica nesta revisão. Nesta etapa foi apenas atualizado o link para abrir o folder de uma página, com parâmetro de versão para evitar a cópia anterior em cache.

- Aplicação em `index.html`, HTML5, Tailwind via CDN oficial e JavaScript Vanilla. Sem backend, banco ou build da aplicação.
- Menu mobile por teclado, Escape e fechamento após navegação; link para pular e âncoras válidas.
- Testador com as quatro categorias, padrões previsíveis, mostrar/ocultar, limpeza e estado inicial; testes somente com exemplos fictícios.
- Nenhuma requisição durante senha/quiz/checklist nos testes anteriores. Sem cookies ou chaves de localStorage/sessionStorage. Entrada fora de logs e URL.
- Quiz: oito combinações de acertos/erros, pontuações 0/3 a 3/3, bloqueio de repetição e reinício.
- Checklist: marcar/desmarcar e teclado. Estado descartado ao recarregar.
- Compartilhamento: formação dos destinos WhatsApp/LinkedIn/mailto e cópia/alternativa testada em origem HTTPS controlada, sem enviar mensagens. Uso real nos aplicativos permanece teste manual.
- Semestre **2026/2** conferido em cabeçalho, identificação, ficha acadêmica, rodapé e PDF atualizado.
- Cinco larguras de referência sem overflow e preferência de movimento reduzido respeitada.
- Auditoria anterior do site: 35 regras aprovadas e zero violações automáticas em 375 e 1440 px e no estado interativo avaliado; itens de contraste sobre gradientes/SVG requerem revisão humana.
- Fonte dos PNGs oficiais e enquadramento do curso documentados em `assets/ORIGEM.md`. Nenhum logo fabricado.

## Publicação e limites

O workflow de GitHub Pages publica a página, o folder HTML, o PDF de uma página e o PNG. O resultado remoto da versão atual está em `PUBLICACAO.md`. Não confunda commit/push com implantação concluída.

A rede do ambiente bloqueou consultas diretas à API do GitHub, ao domínio do Pages e às fontes externas em etapas anteriores. A publicação é acompanhada pela página pública de Actions. Abertura `file://` foi bloqueada pela política do navegador; execução por HTTP foi validada.

Tailwind Play CDN é recomendado para desenvolvimento. O PDF exportado não tem marcação semântica completa nem preparação de gráfica certificada; HTML e texto são alternativas de leitura. A logo ATITUS fornecida tem 140 × 48 px: para impressão ampliada, revise a prova ou solicite um original vetorial/de maior resolução.

## Revisão manual pendente

1. Testar o QR com celulares diferentes e em prova impressa de tamanho real; conferir contraste, margens, créditos e requisitos de sangria/perfil de cor da gráfica.
2. Conferir o site publicado em navegadores e dispositivos reais; testar leitores de tela, zoom de 200%/400% e preferências de fonte/contraste. Auditoria automática não equivale a certificação WCAG.
3. Abrir as referências em rede permitida e testar os compartilhamentos reais por escolha do usuário.
4. Ao postar o PNG, incluir link clicável na legenda e descrição textual; não depender só de imagem ou QR. Nenhuma postagem social ou entrega acadêmica foi realizada automaticamente.

## Publicação da versão de uma página

Confirmada pelo GitHub Actions: execução https://github.com/mateuszilio225/atividade-desafio-da-profissao/actions/runs/42134144481, status **Success**, duração de 19 segundos, commit bb92062. O artefato publicado inclui o folder HTML, o PDF de uma página e a imagem PNG. O link do site foi atualizado para abrir explicitamente a versão de uma página.
