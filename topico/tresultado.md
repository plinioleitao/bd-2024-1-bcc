## Resultado

Clique [AQUI](../media/bd-2024-1-bcc-resumo.pdf) para ver as notas.

#### Avaliação em 10/04/2024
São identificadas duas chaves candidatas em ARTISTA. Um mesmo artista pode atuar em diversos eventos. Um mesmo evento pode ter diversos artistas que atuam no evento. O atributo id em ARTISTA e id em EVENTO possuem a mesma restrição de domínio.

#### Avaliação em 17/04/2024
Quantas cópias do livro intitulado ... LIVRO_COPIAS (Cod_livro) REFERENCES LIVRO (Cod_livro) ...
LIVRO_COPIAS (Cod_unidade) REFERENCES UNIDADE_BIBLIOTECA (Cod_unidade)<br>
Recupere o nome de todos os usuários ... LIVRO_EMPRESTIMOS (Nr_cartao) REFERENCES USUARIO (Nr_cartao)<br>
Para cada livro que é emprestado da unidade ... LIVRO_EMPRESTIMOS (Cod_unidade) REFERENCES UNIDADE_BIBLIOTECA (Cod_unidade) ... LIVRO_EMPRESTIMOS (Cod_livro) REFERENCES LIVRO (Cod_livro) ... LIVRO_EMPRESTIMOS (Nr_cartao) REFERENCES USUARIO (Nr_cartao)<br>
Para cada unidade da biblioteca, recupere ... LIVRO_EMPRESTIMOS (Cod_unidade) REFERENCES UNIDADE_BIBLIOTECA (Cod_unidade)<br>
Recupere o nome, endereço e número ... LIVRO_EMPRESTIMOS (Nr_cartao) REFERENCES USUARIO (Nr_cartao)<br>
Para cada livro cujo autor (ou coautor) ... LIVRO_AUTOR (Cod_livro) REFERENCES LIVRO (Cod_livro) ... LIVRO_COPIAS (Cod_unidade) REFERENCES UNIDADE_BIBLIOTECA (Cod_unidade) ... LIVRO_COPIAS (Cod_livro) REFERENCES LIVRO (Cod_livro)

