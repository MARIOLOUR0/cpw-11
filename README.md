# cpw-11

## Aula 9 — Galeria

A galeria usa o áudio de treino `media/sinal.mp3`, o vídeo de treino
`media/oficina.mp4` e o cartaz `imagens/capa-video.png`. O áudio é um sinal
sintético original; o vídeo é uma animação original de uma oficina fictícia.
Os três ficheiros foram criados localmente para este projeto; não são ficheiros
fornecidos pela plataforma H5P.

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
