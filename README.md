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

Os valores foram personalizados para este clube: a cor de fundo (`#f1f5f9`)
suaviza o fundo branco do navegador; a cor principal (`#006d77`) dá às ligações
uma identidade comum; a largura máxima de `68rem` limita o comprimento das
linhas; e o espaçamento de `2rem` em redor do conteúdo torna a leitura menos
compacta. O guião da primeira aula pede autenticação no Moodle, por isso o CSS
foi definido a partir do objetivo desta tarefa, não de valores de exemplo a
que não foi possível aceder.

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
- Commit, envio e teste da versão publicada com CSS: pendentes.
