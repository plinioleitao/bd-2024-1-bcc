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

#### Avaliação em 12/06/2024
1. RESULT ← π <sub>FUN.Pnome, SUP.Pnome</sub> ( ρ FUN (FUNCIONARIO) ⋈ <sub>FUN.Cpf_supervisor = SUP.CPF</sub> ρ SUP (FUNCIONARIO) )
1. JOAO_CPF ← π <sub>Cpf</sub> ( σ <sub>Pnome="Joao" &#8743; Unome="Silva"</sub> (FUNCIONARIO) )<br>
JOAO_DEPENDENTES ← π <sub>Nome_dependente</sub> ( JOAO_CPF ⋈ <sub>JOAO_CPF.Cpf = DEPENDENTE.Fcpf</sub> DEPENDENTE )<br>
TODOS_DEPENDENTES ← π <sub>Pnome, Nome_dependente</sub> ( FUNCIONARIO ⋈ <sub>FUNCIONARIO.Cpf = DEPENDENTE.Fcpf</sub> DEPENDENTE )<br>
RESULT ← TODOS_DEPENDENTES &#247; JOAO_DEPENDENTES<br>
<sup>Não considera funcionários homônimos e dependentes homônimos.</sup>
1. PROJETOS_FUNC (Cpf, Qtde_projetos) ← Fcpf ℑ CONTA Fcpf ( TRABALHA_EM )<br>
PROJETOS_FUNC_DOIS ← σ <sub>Qtde_projetos=2</sub> ( PROJETOS_FUNC )<br>
RESULT ← π <sub>Pnome</sub> ( PROJETOS_FUNC_DOIS ⋈ <sub>PROJETOS_FUNC_DOIS.Cpf = FUNCIONARIO.Cpf</sub> FUNCIONARIO )

#### Avaliação em 19/06/2024
1. SELECT DISTINCT Pessoa<br>
FROM VENDE NATURAL JOIN GOSTA<br>
WHERE Bar = 'Pipoca'<br>
&nbsp;&nbsp;&nbsp;&nbsp;_Outra alternativa ..._<br>
SELECT DISTINCT Pessoa<br>
FROM GOSTA<br>
WHERE Cerveja IN (<br>
&nbsp;&nbsp;&nbsp;&nbsp;SELECT Cerveja FROM VENDE<br>
&nbsp;&nbsp;&nbsp;&nbsp;WHERE Bar = 'Pipoca' )
2.
