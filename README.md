# CyberSafe — Sua segurança começa com conhecimento

Landing page educativa sobre Ética Hacker e Higiene Digital. Projeto acadêmico da ATITUS EDUCAÇÃO, curso de Ciência da Computação, disciplina Desafio da Profissão, docente Prof. Dr. Suellen Spinello Sotille, semestre 2026/2.

> Projeto acadêmico da disciplina de Desafio da Profissão / Prof. Dr. Suellen S. Sotille - Semestre 2026/2

Integrantes: Mateus Zilio e Yuri Antonini. A identidade CyberSafe não é uma marca institucional oficial.

## Entregas

1. `index.html`: aplicação completa, HTML5 semântico, Tailwind CSS via CDN, CSS complementar e JavaScript Vanilla inline.
2. `FOLDER.md`: texto integral e roteiro de diagramação; `folder.html`: folder diagramado de uma única página/face; `folder-cybersafe.pdf`: PDF A5 de uma página, com QR na frente, chamada para o desafio, logos e integrantes. `folder-cybersafe.png` é a versão em imagem para divulgação. Confirme a implantação antes de divulgar.
3. Este guia: execução, privacidade, manutenção e publicação no GitHub Pages.
4. `VALIDACAO.md`: verificações realizadas, evidências e testes manuais pendentes.

## Abrir e demonstrar

Abra `index.html` diretamente no navegador, com acesso à internet para o Tailwind. Nenhuma instalação, Node.js, npm, API, banco de dados ou backend é necessário. Para servir por HTTP, opcionalmente use um servidor estático que já tenha disponível, como `python3 -m http.server 8000 --bind 127.0.0.1` na pasta do projeto. Python também não é requisito para a publicação.

O conteúdo, os ícones e o código das interações estão no próprio HTML. O único script externo da aplicação é o Play CDN oficial do Tailwind v4, com versão fixada em `https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4.1.18`. A integração segue a documentação https://tailwindcss.com/docs/installation/play-cdn. Não há fontes remotas, analytics ou rastreadores adicionados pelo projeto.

**Limitação do Play CDN:** o Tailwind recomenda esse modo para desenvolvimento, não para produção. Ele exige rede, executa código de terceiro no navegador e gera estilos durante a execução. Esta entrega mantém o CDN para atender ao requisito acadêmico. Para uma implantação de produção, uma tarefa posterior deve compilar o CSS e hospedá-lo localmente, com revisão de segurança e desempenho. O CSS complementar preserva a leitura e as interações principais se o CDN falhar, mas algumas utilidades de layout dependem dele. A abertura local em `file:` pode ter diferenças entre navegadores; o GitHub Pages serve por HTTPS.

## Recursos e privacidade

- O testador exige exemplos fictícios. Usa uma heurística local que prioriza comprimento, reduz a classificação de padrões óbvios/repetidos e compara uma pequena lista de senhas comuns. Não é uma auditoria criptográfica nem consulta vazamentos. Uma frase famosa ou reutilizada pode receber avaliação indevidamente alta.
- A entrada não é enviada, registrada em logs, persistida, inserida na URL nem copiada. O botão Limpar, a saída e a restauração da página limpam o estado. O código não acessa cookies, `localStorage` ou `sessionStorage`.
- O quiz e a checklist mantêm estado somente em memória. Não coletam dados ou guardam respostas. Recarregar ou sair reinicia os recursos.
- O CDN e o serviço de hospedagem recebem as requisições técnicas necessárias ao carregamento da página. Isso é distinto de transmitir entradas do testador; nenhum código do projeto transmite essas entradas. Scripts externos executam com acesso à página: por isso use somente exemplos fictícios e considere a recomendação de CSS compilado para produção.
- Compartilhar exige clique. Usa a URL atual sem query string ou fragmento; não inclui entradas ou respostas. Em `file:` e localhost informa que é necessário publicar, sem gerar endereço fictício. WhatsApp e LinkedIn abrem seus serviços externos; e-mail usa o aplicativo do dispositivo. A cópia requer Clipboard API permitida ou oferece um campo selecionável como alternativa. O código não lê a área de transferência.
- Não há proteção absoluta prometida nem resultados de aprendizagem apresentados como comprovados. Os objetivos PBL não foram avaliados com participantes.

O JavaScript está organizado em funções comentadas em português: menu, análise e apresentação da senha, fluxo do quiz, checklist, compartilhamento e limpeza do estado. SVGs inline são ilustrações originais do projeto.

## Publicar no GitHub Pages

### 1. Criar ou reutilizar o repositório

O repositório indicado para este projeto é `mateuszilio225/atividade-desafio-da-profissao`. Use-o se você tiver permissão. Caso precise de outro, no GitHub entre na sua conta, clique em **New repository**, escolha o nome e a visibilidade compatível com o seu plano do GitHub Pages, e crie-o. Um repositório público costuma ser o caminho mais simples para uma entrega acadêmica, mas só publique arquivos e dados que possam ser públicos.

### 2. Adicionar os arquivos

Na raiz, use **Add file → Upload files** para enviar `index.html`, `folder.html`, `FOLDER.md`, `README.md`, `VALIDACAO.md`, `REQUISITOS-PDF.md`, `folder-cybersafe.pdf`, `folder-cybersafe.png` e a pasta `assets/`. As logos da página e do folder também estão embutidas nos respectivos HTMLs, sem dependência dessa pasta para exibição. Confira os arquivos e faça o commit em `main`. No repositório inicialmente vazio, esse commit pode ser o primeiro a criar a branch. Se o repositório usar outra branch, selecione-a na etapa seguinte. Também é possível usar Git normalmente; não é necessário fazer build.

Mantenha o nome `index.html` em minúsculas, na raiz da branch escolhida. Os documentos são apoio; a aplicação principal continua inteiramente no HTML.

### 3. Publicação automática

O arquivo `.github/workflows/pages.yml` publica os arquivos estáticos com as actions oficiais do GitHub Pages a cada push em `main`. Não há instalação ou build da aplicação. O workflow prepara apenas `index.html`, `folder.html`, `folder-cybersafe.pdf` e `folder-cybersafe.png`; as imagens estão embutidas nos HTMLs.

A action `configure-pages` está configurada para tentar habilitar o Pages. Se o GitHub negar a habilitação automática por falta de privilégios do `GITHUB_TOKEN`, o proprietário deve escolher **Settings → Pages → Source → GitHub Actions** e executar novamente o workflow. Isso é uma configuração do repositório, não uma dependência da aplicação.

### 4. Endereço do projeto e confirmação

Destino configurado no QR e no link do folder:

> https://mateuszilio225.github.io/atividade-desafio-da-profissao/

A raiz desse endereço serve o `index.html`. Confira a execução **Publicar CyberSafe no GitHub Pages** em **Actions** e a URL exibida em **Settings → Pages**. A existência do workflow, de um commit ou de um QR correto não comprova que a implantação terminou. Abra a URL em uma janela anônima e rede móvel antes de divulgar.

### 5. QR Code e folder

O QR foi gerado localmente para a URL acima, sem API externa, e está embutido no folder. Também há versões SVG e PNG em `assets/`. A leitura automática do PNG e do PDF exportado foi validada; confira `VALIDACAO.md`. O destino não é o site do CERT.br, que aparece apenas como fonte educativa.

O link escrito e o clicável no PDF apontam para o mesmo endereço do QR. Se o endereço mudar, regenere os dois arquivos de QR e a incorporação no HTML, atualize o link e reexporte o PDF. Teste com câmeras de celulares diferentes e em prova impressa.

## Antes da entrega acadêmica

Os nomes **Mateus Zilio** e **Yuri Antonini** estão aplicados na página, no folder e nos créditos dos documentos. As logos foram extraídas do PowerPoint enviado, sem redesenho; veja `assets/ORIGEM.md`. O curso usa o mesmo enquadramento do slide, sem exibir a antiga marca IMED presente à direita da imagem completa. O semestre foi corrigido para **2026/2**, conforme a atualização do usuário, em todo o site, folder e documentos. A identificação baseada no PDF, com o semestre corrigido pelo usuário, aparece na seção acadêmica do site. O folder agora usa uma única identificação completa na mesma face do QR, e a redação do prompt anterior foi atualizada para 2026/2 no rodapé do site e no folder.

O PDF prevê **19/11**, sem ano especificado, para finalizar, apresentar, postar nas redes sociais e entregar. Isso é uma etapa acadêmica prevista, não uma afirmação de entrega/publicação. Consulte `REQUISITOS-PDF.md` para a correspondência entre regras e implementação.

A rede deste ambiente bloqueou a API do GitHub e o domínio do Pages durante a preparação (CONNECT 403). Os domínios `api.github.com` e `mateuszilio225.github.io` foram adicionados ao rascunho da configuração de rede; salvar esse rascunho não altera automaticamente a instância. Acompanhe a situação real da publicação em `PUBLICACAO.md`. Não confunda esse rascunho do ambiente com a publicação do site no GitHub Pages.

Consulte `VALIDACAO.md` para os testes de software. Revise conteúdo, legibilidade impressa e navegação com tecnologias assistivas com pessoas reais antes da divulgação ampla. Não declare conformidade integral com WCAG ou resultados de aprendizagem sem avaliação apropriada.
