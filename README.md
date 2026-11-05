# cpw-11

## Aula 9 — Galeria

A galeria usa o áudio de treino `media/sinal.mp3`, o vídeo de treino
`media/oficina.mp4` e o cartaz `imagens/capa-video.png`. O áudio é um sinal
sintético original; o vídeo é uma animação original de uma oficina fictícia.
Os três ficheiros foram criados localmente para este projeto; não são ficheiros
fornecidos pela plataforma H5P.

## Aula 10 — Identidade visual

O ficheiro `estilos.css` é partilhado pela página inicial e pela galeria.
O fundo azul-claro separa o conteúdo, os cartões brancos destacam as secções e
o azul-petróleo identifica os títulos e as ligações. A tipografia do sistema,
o espaçamento generoso, os cantos arredondados e os controlos de mídia
adaptáveis tornam as páginas mais confortáveis de ler em ecrãs diferentes.

Face ao exemplo do guião, foram alterados mais de três valores: o fundo
`#faf9f6` passou a `#f1f5f9`, criando uma tonalidade azul-clara; o texto
`#202b35` passou a `#243447`; a fonte Arial passou para a família do sistema;
o título `#215a89` passou a azul-petróleo; e as ligações `#174f78` passaram a
`#006d77`. A margem simples de 24 px foi substituída por um conteúdo centrado
e responsivo, com largura máxima de `68rem` e espaçamento confortável.

### Registo de testes

- Validação local com Nu HTML Checker: os sete documentos HTML passaram sem
  erros. A validação detetou cercas de Markdown indevidas em
  `paginas/atividades.html`; foram removidas e a validação foi repetida.
- Navegador: o sinal MP3 e o vídeo MP4 carregaram e começaram a reproduzir; os
  controlos estão disponíveis, não há reprodução automática e o cartaz aparece.
- Teste de caminho inválido: o áudio falhou ao carregar (`networkState` 3). O
  caminho original foi reposto e o áudio carregou novamente sem erro.
- Navegação interna para a galeria e ligação de regresso ao início verificadas.
- Publicação: a primeira tentativa compilou o site mas falhou durante o deploy
  com HTTP 500 no GitHub. Uma nova execução terminou com sucesso.
- Site publicado: a página inicial e a galeria abriram. No navegador, os dois
  ficheiros de mídia carregaram (`readyState` 4) e começaram a reproduzir; não
  houve erros e o cartaz do vídeo carregou.
- Os commits da galeria e da publicação foram enviados para `origin/main`.

**Conclusão:** a galeria e a navegação estão completas e os testes locais
e no site publicado passaram. Os ficheiros de mídia são originais e foram
gerados para este projeto.

### Registo de testes de CSS

- Página inicial e galeria: ambas carregam `estilos.css`; o fundo, a cor das
  ligações e o cabeçalho foram confirmados no navegador.
- Cor partilhada: alterar temporariamente `--color-primary` de `#006d77` para
  `#b00020` mudou a cor das ligações nas duas páginas. O valor original foi
  reposto.
- Falha de caminho: trocar temporariamente o href da página inicial por um
  ficheiro CSS inexistente produziu um erro de carregamento e deixou os estilos
  não aplicados. O caminho `estilos.css` foi reposto.
- Nu HTML Checker: os sete documentos continuam válidos.
- O commit `275e2df` foi enviado para `origin/main`.
- GitHub Pages: a compilação e publicação da versão com CSS terminaram com
  sucesso.
- Navegador no site publicado: a página inicial e a galeria carregam o CSS
  comum e apresentam as mesmas cores de fundo, ligações e cabeçalho.

## Aula 11 — Cartões das atividades

Na página de atividades, as oficinas de páginas web, programação e robótica e
programação de jogos usam `article` com a classe comum `cartao`. Uma única regra
em `estilos.css` dá-lhes fundo azul-claro, preenchimento interior, contorno e
cantos arredondados; a margem inferior separa os cartões entre si.

### Registo de testes

- Atividades carrega a folha externa; os três `article.cartao` recebem a regra
  comum de preenchimento, contorno, espaçamento e cantos.
- Alterações isoladas de `padding`, `border` e `margin-bottom`: verificadas no
  navegador; cada alteração refletiu-se nos três cartões.
- Alteração temporária da cor de fundo comum: os três cartões mudaram juntos;
  o estilo original foi reposto.
- A janela estreita revelou que a imagem da oficina ultrapassava o cartão; a
  imagem foi limitada à largura do cartão. Com viewport de 390 px, o documento
  ficou com 375 px de largura, sem overflow horizontal.
- A página inicial e a página de atividades abriram no navegador; o recurso da
  imagem da oficina carregou.
- Nu HTML Checker: `paginas/atividades.html` sem erros. `git diff --check` sem
  problemas.

## Aula 12 — Flexbox nas atividades

Os três cartões estão agrupados em `.cartoes-atividades`, um contentor Flexbox
com espaçamento entre cartões e quebra automática de linha. Cada cartão usa
`flex: 1 1 17rem` para partir de uma largura de referência de 17rem e adaptar-se
ao espaço disponível.

### Registo de testes

- Janela larga (1280 px): três cartões na mesma linha, cada um com cerca de
  330 px.
- Janela estreita (390 px): cartões empilhados, com cerca de 301 px; textos
  mantêm-se legíveis e não há deslocamento horizontal (documento com 375 px).
- O contentor apresenta `display: flex`, `flex-wrap: wrap` e 16 px de intervalo;
  a imagem da oficina carregou.
- Nu HTML Checker e `git diff --check`: sem erros.
