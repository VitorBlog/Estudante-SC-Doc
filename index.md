![haha](https://www.infoescola.com/wp-content/uploads/2009/12/bandeira-de-santa-catarina.jpg)

### Point

<code>
http://webservices.sed.sc.gov.br/eol2/rest/
</code>

### Pegar dados do aluno

Dados necessários: Matricula;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaEscolaAluno
// Exemplo:
curl -XPOST -H "Content-type: application/json" -d '{"AlunoCod": 237590466}' 'http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaEscolaAluno'
```

Retorno:

```javascript
{"ResultadoAluno":"[{\"AlunoNom\":\"Nome completo\",\"AlunoDataNasc\":\"Data de nascimento\",\"AlunoCod\":Matricula,\"UeCod\":Código da escola,\"UeNom\":\"Nome da escola\",\"UeEnd\":\"Rua da escola\",\"UeNumEnd\":Numero de endereço,\"UeMunNom\":\"Município\",\"UeLatitude\":\"Latitude\",\"UeLongitude\":\"Longitude\"}]"}
```

### Pegar boletim do aluno

Dados necessários: Matricula;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaBoletim
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_boletim_geral.php?matricula=237590466
```

Retorno:

```javascript
{"ResultadoBoletim":"[{\"Turma\":\"Turma\",\"AlunoCod\":Matricula,\"AlunoDataNasc\":\"Data de nascimento\",\"AlunoCEJA\":\"n\",\"NotaFaltaDisciplina\":[{{\"DisciplinaNome\":\"LÍNGUA ESTRANGEIRA - INGLÊS\",\"DisciplinaCodigo\":319,\"Nota1\":10.0000,\"Falta1\":2,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"n\",\"Liberado3\":\"n\",\"Liberado4\":\"n\",\"LiberadoExame\":\"n\",\"LiberadoRec\":\"n\"}]}]"}
//OBS: sai uma linha dessa para cada materia
```

### Pegar grade do aluno

Dados necessários: Matricula;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaGradeAluno'
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_grade_aluno.php?matricula=237590466
```

Retorno:

```javascript
{"ResultadoAluno":"[{\"Turma\":\"Turma\",\"AlunoCod\":Matricula,\"dsiciplinas\":[{\"Cd\":\"255\",\"Nm\":\"BIOLOGIA                                \"},{\"Cd\":\"301\",\"Nm\":\"MATEMÁTICA                              \"},{\"Cd\":\"302\",\"Nm\":\"GEOGRAFIA                               \"},{\"Cd\":\"304\",\"Nm\":\"HISTÓRIA                                \"},{\"Cd\":\"307\",\"Nm\":\"EDUCAÇÃO FÍSICA                         \"},{\"Cd\":\"319\",\"Nm\":\"LÍNGUA ESTRANGEIRA - INGLÊS             \"},{\"Cd\":\"401\",\"Nm\":\"LÍNGUA PORTUGUESA E LITERATURA          \"},{\"Cd\":\"437\",\"Nm\":\"SOCIOLOGIA                              \"},{\"Cd\":\"475\",\"Nm\":\"FÍSICA                                  \"},{\"Cd\":\"513\",\"Nm\":\"QUÍMICA                                 \"},{\"Cd\":\"536\",\"Nm\":\"FILOSOFIA                               \"},{\"Cd\":\"628\",\"Nm\":\"ARTE                                    \"}]}]"}
//Santa Catarina representando como sempre. "dsiciplinas"
```

### Pegar a nota do aluno

Dados necessários: Matricula, Código da materia (Retornado na Grade), Código da turma (Retornado na Grade e no Boletim);
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaNotasDisci
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_notas.php?matricula=237590466&disc=319
```

Retorno:

```javascript
{"ResultadoNotas":"{\"DisciplinaNom\":\"LÍNGUA ESTRANGEIRA - INGLÊS\",\"AlunoCod\":Matricula,\"DtNascimento\":\"Data de nascimento\",\"UeNom\":\"Escola",\"NotasTurma\":\"Turma\",\"AlunoSemNota\":false,\"NotaWS\":[{\"AtividadesBimestre\":1,\"AtividadesCod\":104,\"AtividadesDescricao\":\"IT1\",\"AtividadesData\":\"2019-05-10\",\"TiposAtividadeDescricao\":\"Interpretação de texto\",\"AtividadeNota\":10.0000,\"AtividadeMediaTurma\":9.5200}]}"}
```

### Pegar faltas do aluno

Dados necessários: Matricula;
```php
http://estudantesc.sc.gov.br/ws/get_faltas.php?matricula=MATRICULA
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_faltas.php?matricula=237590466
```

Retorno:
###
```javascript
[{"DisciplinaNom":"BIL - BIOLOGIA","QtdFaltas":0},{"DisciplinaNom":"MAT - MATEMÁTICA","QtdFaltas":2},{"DisciplinaNom":"GEO - GEOGRAFIA","QtdFaltas":0},{"DisciplinaNom":"HIS - HISTÓRIA","QtdFaltas":0},{"DisciplinaNom":"EFI - EDUCAÇÃO FÍSICA","QtdFaltas":1},{"DisciplinaNom":"LEI - LÍNGUA ESTRANGEIRA - INGLÊS","QtdFaltas":2},{"DisciplinaNom":"LPL - LÍNGUA PORTUGUESA E LITERATURA","QtdFaltas":1},{"DisciplinaNom":"SOC - SOCIOLOGIA","QtdFaltas":1},{"DisciplinaNom":"FIS - FÍSICA","QtdFaltas":0},{"DisciplinaNom":"QUI - QUÍMICA","QtdFaltas":2},{"DisciplinaNom":"FIL - FILOSOFIA","QtdFaltas":0},{"DisciplinaNom":"ATE - ARTE","QtdFaltas":2}]
```
<br>
<center>
  <h1><strong>Exemplos com código</strong></h1>
</center>
<br>
### Exemplo com PHP e cURL

```php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'http://estudantesc.sc.gov.br/ws/{ API_CALL }');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
$data = curl_exec($ch);
curl_close($ch); 
$result = json_decode($data, true);
```


### Exemplo com  e XMLHttpRequest

```javascript
var xhttp = new XMLHttpRequest();
xhttp.open("GET","https://estudantesc.sc.gov.br/ws/{ API_CALL }", true);
xhttp.send();
var rt = xhttp.responseText;
```
