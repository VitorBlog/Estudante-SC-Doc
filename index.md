![haha](https://www.infoescola.com/wp-content/uploads/2009/12/bandeira-de-santa-catarina.jpg)

# Point

<code>
http://estudantesc.sc.gov.br/ws/
</code>

# Pegar dados do aluno

Dados necessários: Matricula, Data de nascimento;
```
http://estudantesc.sc.gov.br/ws/get_dados_aluno.php?matricula=MATRICULA&datanas=DATA DE NASCIMENTO
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_dados_aluno.php?matricula=237590466&datanas=12042000
```

Retorno:

```
[{"AlunoNom":"NOME COMPLETO","UeCod":CÓDIGO,"UeNom":"ESCOLA","UeEnd":"RUA","UeNumEnd":NUMERO,"UeMunNom":"CIDADE"}]
```
