# Origem e aplicação das logos

Os dois PNGs foram extraídos diretamente do arquivo enviado pelo usuário, `caf2ff8c-f378-4c98-9a9e-a558444edfc2.pptx`. Não foram gerados, redesenhados, recoloridos ou reamostrados.

| Arquivo | Origem no PowerPoint | Dimensões | SHA-256 |
|---|---|---|---|
| `atitus-educacao-original.png` | `ppt/media/image4.png` | 140 × 48 px, RGBA | `8b9762598d11ef86e61704bbac8989946128dff17fbfb6ea7bacee486e5eff94` |
| `ciencia-da-computacao-original.png` | `ppt/media/image3.png` | 1197 × 181 px, RGBA | `694a16116fe587fa89e3e820ce415a7ea08459f546a868da2c904943fb6814d2` |

A logo branca ATITUS EDUCAÇÃO é usada sobre fundo marinho, com altura automática e largura inferior à original no site. Sem filtros, distorção ou alteração das cores. Para impressão ampliada, o PNG de 140 px pode ser insuficiente; solicite uma versão vetorial/de maior resolução e valide uma prova.

A imagem completa do curso contém “Ciência da Computação” à esquerda e a antiga marca IMED à direita. O próprio slide fornecido exibe apenas o curso: em `ppt/slides/slide1.xml`, o objeto que referencia `image3.png` tem `a:srcRect r="37365"`, isto é, oculta 37,365% da lateral direita. O projeto reproduz esse enquadramento, sem alterar o arquivo original: SVG com viewport `0 0 749.74095 181` e imagem interna de `1197 × 181`. O exemplo de folder na página 7 do PDF também mostra a arte do curso sem IMED. Em Canva/Figma, use uma máscara com a mesma proporção, mantendo a escala da imagem e exibindo a área esquerda. Não estique a arte completa para caber.

Nos HTMLs, as imagens são embutidas como `data:image/png;base64` para manter cada material independente de arquivos externos. O SVG do curso apenas enquadra um PNG; não converte a arte em desenho vetorial.

O material recebido permite identificar as artes utilizadas no trabalho; não inclui um manual completo de marca nem estabelece uma licença geral de redistribuição. O uso aqui atende ao projeto acadêmico solicitado. Espaçamento e fundo são escolhas de layout; não são apresentados como medidas oficiais de um manual não fornecido.

## QR Code do projeto

`qrcode-cybersafe.svg` e `qrcode-cybersafe.png` foram gerados localmente com Segno 1.6.6, correção de erro H e zona livre de quatro módulos. Destino: https://mateuszilio225.github.io/atividade-desafio-da-profissao/

O usuário esclareceu que o QR deve abrir o `index.html` do projeto. Por isso o padrão foi regenerado para essa URL, em vez de reutilizar a imagem anterior associada à Cartilha CERT.br. A leitura foi validada com ZXing-C++ 2.3.0; as ferramentas são de preparação/QA e não são dependências da aplicação.
