# Checklist de validação — CyberSafe

Verificação realizada em 05/11/2026, em Chromium headless disponível no ambiente, controlado por Playwright. A aplicação foi servida estaticamente por HTTP. As ferramentas de QA são externas à aplicação e não precisam ser instaladas para utilizá-la.

Resultado da execução final: **23 verificações aprovadas e 1 bloqueada**, sem falhas nos fluxos executados. Uma verificação pode abranger vários casos; esses números não representam participantes nem resultados de aprendizagem. Esta execução foi repetida após a leitura do PDF e a inclusão das logos, de Mateus Zilio e Yuri Antonini e do folder diagramado. Inclui os fluxos originais e a exportação do novo folder. As imagens embutidas foram comparadas byte a byte aos PNGs extraídos do PowerPoint, sem alterações.

## Critérios do enunciado

| # | Critério | Resultado e evidência |
|---|---|---|
| 1 | HTML abre corretamente | **Aprovado por HTTP.** Título e conteúdo carregados em Chromium. Abertura direta por `file://` **bloqueada** com `ERR_BLOCKED_BY_ADMINISTRATOR` pela política do navegador gerenciado; testar em navegador pessoal. |
| 2 | Tailwind carrega | **Aprovado.** Requisição real ao CDN v4.1.18 e verificação de uma utilidade `grid` aplicada no layout PBL. Sem falhas de recursos na página principal. |
| 3 | Layout responsivo | **Aprovado nas verificações executadas.** Larguras de 320, 375, 768, 1024 e 1440 px, sem rolagem horizontal do documento. Repetido com todos os detalhes expandidos; controles visíveis permaneceram dentro da largura. Capturas de 375 e 1440 px revisadas visualmente. |
| 4 | Âncoras e navegação | **Aprovado.** Todos os destinos internos existem e os IDs são únicos. Todos os links do menu foram acionados, com confirmação do fragmento e foco na seção correspondente. CTAs e botão do topo apontam para os destinos corretos. |
| 5 | Menu mobile | **Aprovado.** Abre por Enter, permite Tab até a navegação, fecha com Escape e devolve o foco. Fecha após escolher uma seção e atualiza `aria-expanded`. |
| 6 | Feedback de senha | **Aprovado.** Exemplos fictícios exercitaram as quatro categorias, comprimento, sequência numérica, teclas vizinhas, repetições, senha comum e frase longa. Apagar o texto restaura o estado inicial. |
| 7 | Mostrar/ocultar | **Aprovado.** Alternância entre `password` e `text`, texto do botão e `aria-pressed`. Limpar apaga a entrada, oculta novamente a senha, zera o medidor e devolve foco ao campo. |
| 8 | Privacidade da entrada | **Aprovado nos fluxos observados e revisão do código.** Nenhuma nova requisição durante senha, quiz e checklist. Nenhum cookie ou chave em localStorage/sessionStorage. Entrada não aparece na URL. O código da aplicação não contém envio, persistência ou logs da senha. O estado também é limpo ao recarregar e no evento de saída. |
| 9 | Três perguntas do quiz | **Aprovado.** Uma pergunta por vez; gabarito C, A, B; feedback imediato com explicação. Após responder, os botões ficam desabilitados para impedir pontuação duplicada. |
| 10 | Pontuação | **Aprovado.** Oito combinações de acertos/erros cobriram resultados de 0/3, 1/3, 2/3 e 3/3. |
| 11 | Reiniciar quiz | **Aprovado.** Retorna à primeira pergunta, remove feedback anterior, reabilita opções e reinicia a pontuação. Recarregar a página também reinicia o quiz. |
| 12 | Checklist | **Aprovado.** Marcar os cinco itens e desmarcar um atualiza o contador. Espaço alterna o checkbox por teclado. Recarregar remove as marcações. |
| 13 | Compartilhamento | **Aprovada a formação dos destinos**, em origem HTTPS controlada e interceptada no teste, sem acessar redes sociais ou enviar mensagens. WhatsApp, LinkedIn, cópia e intenção `mailto:` usam a URL atual sem parâmetros/fragmentos. Testados sucesso simulado da Clipboard API, falha com alternativa selecionável e aviso em localhost. **Pendente** a integração real em cada aplicativo após hospedagem. A origem de teste não é uma URL publicada nem aparece no site. |
| 14 | Teclado e acessibilidade | **Aprovados os fluxos exercitados:** link para pular, menu, Escape, expansões, quiz, foco entre perguntas, checkbox, campo e botões de senha. Movimento reduzido confirmado com `scroll-behavior: auto`. Auditoria automática detalhada abaixo; teste com leitores de tela permanece pendente. |
| 15 | Erros JavaScript | **Aprovado.** Zero exceções `pageerror`, zero `console.error` e zero requisições de recursos com falha na página principal. |
| 16 | Logos e integrantes | **Aprovado.** Logos fornecidas aplicadas no cabeçalho, na seção acadêmica, no rodapé e nas duas faces do folder. PNGs embutidos idênticos aos extraídos do PowerPoint. Enquadramento do curso reproduzido do slide, sem IMED no layout. Mateus Zilio e Yuri Antonini substituem os nomes reservados. |
| 17 | Textos acadêmicos | **Aprovado.** Conferidos instituição, curso, disciplina, docente, semestre 2026/2, tema e os nomes reais da dupla. Identificações do pedido original e do PDF preservadas nos respectivos locais, com o semestre atualizado para 2026/2 a pedido do usuário. Título e subtítulo obrigatórios presentes. |
| 18 | Fontes com links válidos | **Parcial.** Há três links HTTPS para os domínios oficiais de CERT.br, NIST e ANPD. A consulta remota foi **bloqueada pelo proxy (CONNECT 403)**; não se afirma que responderam HTTP 200. Abrir os links em rede permitida antes da entrega. A documentação do Tailwind também foi bloqueada, embora o arquivo do CDN tenha carregado normalmente. |
| 19 | Integridade do conteúdo | **Revisão editorial realizada.** Sem estatísticas, pesquisas, resultados, logos ou autorizações fabricados. Exemplos de golpes estão identificados como fictícios. Objetivos PBL são apresentados como esperados, sem pesquisa com participantes. Não há garantia de proteção ou recuperação financeira. |
| 20 | GitHub Pages sem backend | **Publicado.** Commit edf9e8d com semestre 2026/2 implantado com sucesso pelo workflow 42132599185. URL confirmada pela etapa de implantação. A consulta HTTP direta nesta instância permanece bloqueada pelo proxy; detalhes em `PUBLICACAO.md`. |

## Auditoria automática de acessibilidade

Foi usado axe-core 4.10.3, apenas no ambiente de QA; a biblioteca não foi incluída no site.

- Estados iniciais em 375 e 1440 px: **35 regras aprovadas e nenhuma violação automática**, com as tags `wcag2a`, `wcag2aa`, `wcag21aa` e `wcag22aa`.
- Estado interativo com senha de exemplo visível e feedback de alternativa incorreta: **nenhuma violação automática**.
- Uma regra, `color-contrast`, teve itens **inconclusivos**, principalmente no hero com gradiente/pseudoelemento, textos do SVG e cabeçalho fixo. Isso não equivale a aprovação integral do contraste pelo axe.
- Na revisão complementar, foram calculadas razões de contraste dos principais pares: branco sobre azul do CTA **5,17:1**; texto secundário `#526477` sobre branco **6,09:1**; texto do hero `#C5D2DC` sobre a cor mais clara do fundo `#103744` **8,25:1**; título verde `#59DBC7` sobre esse fundo **7,50:1**; texto discreto do SVG `#86A4B5` sobre esse fundo **4,84:1**. Os números dos cards foram ajustados ao mesmo cinza secundário. As razões são verificações de pares de cores, não uma certificação de toda a página.

HTML semântico, um H1, `lang="pt-BR"`, labels, foco visível, mensagens textuais e regiões de status foram conferidos. **Não se declara conformidade integral com WCAG 2.2 AA:** auditoria automática e teste de teclado não substituem avaliação humana e tecnologias assistivas.

## Limitações conhecidas

- Play CDN do Tailwind é recomendado para desenvolvimento, não produção. A versão foi fixada; depende de conexão e de código externo no navegador. A recomendação para uma futura versão de produção está no `README.md`.
- O fallback sem CDN foi exercitado: conteúdo e testador continuam utilizáveis; utilidades do Tailwind ficam indisponíveis.
- A análise de senhas é aproximada, sem consulta a vazamentos. A lista local é pequena e não detecta toda frase famosa, palavra previsível ou reutilização. Use exclusivamente exemplos fictícios.
- Foram usados eventos reais de teclado em navegador automatizado, não testes com participantes ou leitores de tela.
- Além do roteiro, foram produzidos `folder.html` e a prova `folder-cybersafe.pdf`, com **duas páginas A5**, sem conteúdo excedente na validação de impressão do Chromium. QR e link do projeto estão aplicados e validados; a disponibilidade remota deve ser confirmada após a implantação. O PDF exportado não tem marcação semântica (tagged PDF); a versão HTML e o roteiro textual são as alternativas de leitura. A acessibilidade do PDF deve ser trabalhada antes de utilizá-lo como único meio digital.
- A logo ATITUS original mede 140 × 48 px: atende à exibição web utilizada, mas ampliações impressas exigem prova e, preferencialmente, arquivo vetorial/de maior resolução. Não foi inventada uma nova versão da marca.
- O repositório inicialmente estava vazio. O código foi posteriormente enviado e `main` confirmado por Git; a página do repositório respondeu HTTP 200. O acesso direto ao domínio do Pages pelo ambiente não pôde ser confirmado: o proxy bloqueou a consulta com CONNECT 403. Após o usuário solicitar a publicação, o QR foi gerado para o endereço padrão do Pages do repositório e a publicação automática foi configurada. A conclusão remota não foi presumida; veja `PUBLICACAO.md`.
- O ambiente não permitiu a abertura direta `file://` nem a conferência HTTP das referências oficiais. Essas limitações foram preservadas, sem contornar a política.

## Revisão manual pendente

1. Abrir o HTML localmente em um navegador pessoal; conferir Safari, Firefox, Android e iOS. Testar zoom a 200% e 400%, preferências de contraste e tamanhos de fonte personalizados.
2. Percorrer toda a página com NVDA/Firefox ou VoiceOver/Safari. Conferir anúncio do medidor, feedback do quiz, foco, landmarks e estados do menu.
3. Revisar o contraste nos pontos inconclusivos do axe em diferentes estados/posições, os detalhes da ilustração, foco sobre cada fundo e leitura confortável dos textos menores.
4. Abrir as três referências em uma rede permitida e confirmar destino/conteúdo atual. O bloqueio observado foi no proxy do ambiente, antes de chegar aos sites.
5. Publicar no GitHub Pages e validar o endereço público em janela anônima e rede móvel. Testar pop-ups, WhatsApp, LinkedIn, aplicativo de e-mail e cópia sob as permissões reais do dispositivo, escolhendo se deseja concluir algum compartilhamento.
6. Revisar a legibilidade das logos fornecidas, especialmente em impressão. Os nomes Mateus Zilio e Yuri Antonini e as duas redações de identificação acadêmica já estão aplicados. Se houver manual de marca ou arquivo vetorial oficial adicional, conferir espaçamentos e substituir a fonte raster de baixa resolução sem distorções.
7. Revisar as duas faces já diagramadas e a prova PDF; confirmar a implantação e testar o QR já aplicado; conferir a URL escrita, as margens, a zona livre e a leitura do QR em PDF e prova impressa. Confirmar as especificações de impressão com a gráfica.
8. Se houver avaliação de aprendizagem com participantes, planejar e registrar essa etapa separadamente. Não apresentar a pontuação do quiz como evidência de eficácia do projeto.

## Conferência das novas entregas

- `folder.html` foi testado nas cinco larguras de referência, sem rolagem horizontal do documento. A exportação em A5 foi verificada com `pdfinfo`: duas páginas de 420 × 594,96 pontos. A extração de texto confirmou as três dicas e os nomes em ambas as faces.
- Os PNGs originais têm hashes documentados em `assets/ORIGEM.md`. Foram verificadas três incorporações de cada logo no site e duas no folder, todas idênticas aos bytes originais. O curso mantém a proporção e o enquadramento da apresentação fornecida.
- `REQUISITOS-PDF.md` registra a regra por página e o estado de atendimento. QR e link do projeto foram posteriormente implementados; a disponibilidade remota e a divulgação nas redes sociais não foram apresentadas como concluídas sem evidência.

## Revisão final do QR e das regras do PDF

O PDF de regras foi relido integralmente. Foram conferidos novamente: dupla, dicas de TI, PBL/Ética Hacker, logos ATITUS/curso e identificação acadêmica no site e nas duas faces do folder. O QR foi regenerado para a página `index.html` do projeto, conforme a correção do usuário, e não para o CERT.br.

- Destino: https://mateuszilio225.github.io/atividade-desafio-da-profissao/
- QR gerado localmente, correção H, zona livre de quatro módulos, 32 mm no PDF A5.
- Leitura do PNG e da página renderizada do PDF validada com ZXing-C++: ambas retornaram exatamente a URL do projeto.
- Anotações de link do PDF conferidas com `pdfinfo -url`: QR e URL escrita apontam para o projeto; a referência CERT.br permanece separada.
- Folder novamente verificado nas cinco larguras sem overflow, impressão A5 de duas páginas sem cortes e sem erros de JavaScript.
- A publicação no GitHub Pages foi solicitada e recebeu workflow próprio. A situação remota está em `PUBLICACAO.md`; um QR legível não comprova que a implantação terminou.

O primeiro workflow remoto foi acompanhado pela página pública do GitHub e suas anotações: falha de ativação do Pages por `Resource not accessible by integration`. Esse é um resultado remoto efetivamente observado, separado dos testes locais aprovados. O push não equivale a publicação concluída.

## Correção de semestre solicitada pelo usuário

O semestre foi alterado para **2026/2** em todas as ocorrências do site, folder, PDF exportado e documentos. Esta instrução posterior substitui a indicação do primeiro semestre no enunciado anterior.

Verificações executadas em Chromium: cabeçalho, ficha acadêmica, identificação e rodapé contêm 2026/2; nenhuma ocorrência antiga no conteúdo da página; cinco larguras sem overflow. PDF reexportado em duas faces, com quatro ocorrências de 2026/2 e sem cortes. O QR foi novamente decodificado diretamente da página renderizada do PDF e manteve a URL do projeto.

O 404 mostrado pelo usuário é compatível com o bloqueio de ativação do Pages já diagnosticado: `Resource not accessible by integration` ao criar o site. A aplicação local funciona; a ativação do serviço requer a configuração de fonte no repositório pelo proprietário.

## Resultado da implantação após a correção

A nova execução remota https://github.com/mateuszilio225/atividade-desafio-da-profissao/actions/runs/42132599185 concluiu com **Success** e informou https://mateuszilio225.github.io/atividade-desafio-da-profissao/ como endereço de implantação. O commit edf9e8d contém o semestre 2026/2 e o PDF reexportado. Isso substitui o bloqueio de ativação da primeira execução, mantido acima apenas como histórico do diagnóstico. A consulta HTTPS direta pelo ambiente continuou bloqueada pelo proxy; a publicação foi confirmada pelas evidências do GitHub Actions.
