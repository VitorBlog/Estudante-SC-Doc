![haha](https://www.infoescola.com/wp-content/uploads/2009/12/bandeira-de-santa-catarina.jpg)

### OBS
Tudo pego usando o proxy Charles;

*Olá Jason! Bearer Teste de token Jason*
*Não sei se você vai ler isso, mas aqui esta a foto que eu esqueci de enviar*
<details>
  <summary>Fotona</summary>
  ![jeiso](https://i.ibb.co/nf3hHQ5/f18ed9c8-ab2b-4c16-892c-6b3f1879b88f.jpg)
</details>

#### Como pegar o JSON de verdade
Nem sei como explicar isso, mas para você pegar o JSON de verdade é preciso uma gambiarra;
*Ex wsConsultaEscolaAluno*

Você vai pegar a key "ResultadoAluno" como String, dar Parse de novo como Array e pegar o primeiro elemento como Object (Dependendo da API/Linguagem você vai ter que dar Parse nesse ultimo também)

### Pegar dados do aluno

Dados necessários: Matricula;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaEscolaAluno
// Exemplo:
curl -XPOST -H "Content-type: application/json" -d '{"AlunoCod": 237590466}' 'http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaEscolaAluno'
```

<details>
  <summary>Retorno: </summary>

```javascript
{"ResultadoAluno":"[{\"AlunoNom\":\"VITOR COM NOME FALSO\",\"AlunoDataNasc\":\"0000-00-00\",\"AlunoCod\":665522331,\"UeCod\":43256,\"UeNom\":\"EEB Cidinha te amo\",\"UeEnd\":\"0\",\"UeNumEnd\":"Dado",\"UeMunNom\":\"0\",\"UeLatitude\":\"0\",\"UeLongitude\":\"0\"}]"}
```
</details>

### Pegar boletim do aluno

Dados necessários: Matricula;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaBoletim
// Exemplo:
curl -XPOST -H "Content-type: application/json" -d '{"AlunoCod": 237590466}' 'http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaBoletim'
```

<details>
  <summary>Retorno: </summary>
```javascript
{"ResultadoBoletim":"[{\"Turma\":\"60936-4110-M-3-5\",\"AlunoCod\":237590466,\"AlunoDataNasc\":\"0000-00-00\",\"AlunoCEJA\":\"n\",\"NotaFaltaDisciplina\":[{\"DisciplinaNome\":\"BIOLOGIA\",\"DisciplinaCodigo\":255,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"MATEMÁTICA\",\"DisciplinaCodigo\":301,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"GEOGRAFIA\",\"DisciplinaCodigo\":302,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"HISTÓRIA\",\"DisciplinaCodigo\":304,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"EDUCAÇÃO FÍSICA\",\"DisciplinaCodigo\":307,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"LÍNGUA ESTRANGEIRA - INGLÊS\",\"DisciplinaCodigo\":319,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"LÍNGUA PORTUGUESA E LITERATURA\",\"DisciplinaCodigo\":401,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"SOCIOLOGIA\",\"DisciplinaCodigo\":437,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"FÍSICA\",\"DisciplinaCodigo\":475,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"QUÍMICA\",\"DisciplinaCodigo\":513,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"FILOSOFIA\",\"DisciplinaCodigo\":536,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"},{\"DisciplinaNome\":\"ARTE\",\"DisciplinaCodigo\":628,\"Nota1\":0,\"Falta1\":0,\"Nota2\":0,\"Falta2\":0,\"Nota3\":0,\"Falta3\":0,\"Nota4\":0,\"Falta4\":0,\"NotaExame\":0,\"NotaRecuperacao\":0,\"NotaFinal\":0,\"Liberado1\":\"s\",\"Liberado2\":\"s\",\"Liberado3\":\"s\",\"Liberado4\":\"n\",\"LiberadoExame\":\"s\",\"LiberadoRec\":\"n\"}]}]"}
```
</details>

### Pegar grade do aluno

Dados necessários: Matricula, Turma;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaGradeAluno
// Exemplo:
curl -XPOST -H "Content-type: application/json" -d '{"AlunoCod": 237590466,"turmaParm":""}' 'http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaGradeAluno'
```

<details>
  <summary>Retorno: </summary>

```javascript
{"ResultadoAluno":"[{\"Turma\":\"60936-4110-M-3-5\",\"AlunoCod\":237590466,\"dsiciplinas\":[{\"Cd\":\"255\",\"Nm\":\"BIOLOGIA                                \"},{\"Cd\":\"301\",\"Nm\":\"MATEMÁTICA                              \"},{\"Cd\":\"302\",\"Nm\":\"GEOGRAFIA                               \"},{\"Cd\":\"304\",\"Nm\":\"HISTÓRIA                                \"},{\"Cd\":\"307\",\"Nm\":\"EDUCAÇÃO FÍSICA                         \"},{\"Cd\":\"319\",\"Nm\":\"LÍNGUA ESTRANGEIRA - INGLÊS             \"},{\"Cd\":\"401\",\"Nm\":\"LÍNGUA PORTUGUESA E LITERATURA          \"},{\"Cd\":\"437\",\"Nm\":\"SOCIOLOGIA                              \"},{\"Cd\":\"475\",\"Nm\":\"FÍSICA                                  \"},{\"Cd\":\"513\",\"Nm\":\"QUÍMICA                                 \"},{\"Cd\":\"536\",\"Nm\":\"FILOSOFIA                               \"},{\"Cd\":\"628\",\"Nm\":\"ARTE                                    \"}]}]"}
```
</details>

### Pegar a nota do aluno

Dados necessários: Matricula, Código da materia (Retornado na Grade), Código da turma (Retornado na Grade e no Boletim);
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaNotasDisci
// Exemplo:
curl -XPOST -H "Content-type: application/json" -d '{"AlunoCod":237590466,"DisciCod":"255","turmaParm":"60936-4110-M-3-5"}' 'http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaNotasDisci'
```

<details>
  <summary>Retorno: </summary>

```javascript
{"ResultadoNotas":"{\"DisciplinaNom\":\"\",\"AlunoCod\":237590466,\"DtNascimento\":\"0000-00-00\",\"UeNom\":\"EEB AAAAAAAAA\",\"NotasTurma\":\"60936-4110-M-3-5\",\"AlunoSemNota\":true}"}
```
</details>

### Pegar faltas do aluno

Dados necessários: Matricula;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaFaltas
// Exemplo:
curl -XPOST -H "Content-type: application/json" -d '{"AlunoCod":237590466}' 'http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaFaltas'

<details>
  <summary>Retorno: </summary>

```javascript
{"ResultadoFaltas":"[{\"AlunoCod\":237590466,\"DtNascimento\":\"0000-00-00\",\"Turma\":\"60936-4110-M-3-5\",\"UeCod\":2343,\"UeNom\":\"EEB AAAAAAAAA\",\"QtdTurmas\":0,\"FaltaDisciplinaWs\":[{\"DisciplinaNom\":\"BIL - BIOLOGIA\",\"DisciplinaCod\":255,\"QtdFaltas\":0},{\"DisciplinaNom\":\"MAT - MATEMÁTICA\",\"DisciplinaCod\":301,\"QtdFaltas\":0},{\"DisciplinaNom\":\"GEO - GEOGRAFIA\",\"DisciplinaCod\":302,\"QtdFaltas\":0},{\"DisciplinaNom\":\"HIS - HISTÓRIA\",\"DisciplinaCod\":304,\"QtdFaltas\":0},{\"DisciplinaNom\":\"EFI - EDUCAÇÃO FÍSICA\",\"DisciplinaCod\":307,\"QtdFaltas\":0},{\"DisciplinaNom\":\"LEI - LÍNGUA ESTRANGEIRA - INGLÊS\",\"DisciplinaCod\":319,\"QtdFaltas\":0},{\"DisciplinaNom\":\"LPL - LÍNGUA PORTUGUESA E LITERATURA\",\"DisciplinaCod\":401,\"QtdFaltas\":0},{\"DisciplinaNom\":\"SOC - SOCIOLOGIA\",\"DisciplinaCod\":437,\"QtdFaltas\":0},{\"DisciplinaNom\":\"FIS - FÍSICA\",\"DisciplinaCod\":475,\"QtdFaltas\":0},{\"DisciplinaNom\":\"QUI - QUÍMICA\",\"DisciplinaCod\":513,\"QtdFaltas\":0},{\"DisciplinaNom\":\"FIL - FILOSOFIA\",\"DisciplinaCod\":536,\"QtdFaltas\":0},{\"DisciplinaNom\":\"ATE - ARTE\",\"DisciplinaCod\":628,\"QtdFaltas\":0}]}]"}
```
</details>

### Pegar faltas do aluno

Dados necessários: Matricula;
```php
http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaFaltas
// Exemplo:
curl -XPOST -H "Content-type: application/json" -d '{"AlunoCod":237590466}' 'http://webservices.sed.sc.gov.br/eol2/rest/wsConsultaFaltas'

<details>
  <summary>Retorno: </summary>

```javascript
{"ResultadoFaltas":"[{\"AlunoCod\":237590466,\"DtNascimento\":\"0000-00-00\",\"Turma\":\"60936-4110-M-3-5\",\"UeCod\":2343,\"UeNom\":\"EEB AAAAAAAAA\",\"QtdTurmas\":0,\"FaltaDisciplinaWs\":[{\"DisciplinaNom\":\"BIL - BIOLOGIA\",\"DisciplinaCod\":255,\"QtdFaltas\":0},{\"DisciplinaNom\":\"MAT - MATEMÁTICA\",\"DisciplinaCod\":301,\"QtdFaltas\":0},{\"DisciplinaNom\":\"GEO - GEOGRAFIA\",\"DisciplinaCod\":302,\"QtdFaltas\":0},{\"DisciplinaNom\":\"HIS - HISTÓRIA\",\"DisciplinaCod\":304,\"QtdFaltas\":0},{\"DisciplinaNom\":\"EFI - EDUCAÇÃO FÍSICA\",\"DisciplinaCod\":307,\"QtdFaltas\":0},{\"DisciplinaNom\":\"LEI - LÍNGUA ESTRANGEIRA - INGLÊS\",\"DisciplinaCod\":319,\"QtdFaltas\":0},{\"DisciplinaNom\":\"LPL - LÍNGUA PORTUGUESA E LITERATURA\",\"DisciplinaCod\":401,\"QtdFaltas\":0},{\"DisciplinaNom\":\"SOC - SOCIOLOGIA\",\"DisciplinaCod\":437,\"QtdFaltas\":0},{\"DisciplinaNom\":\"FIS - FÍSICA\",\"DisciplinaCod\":475,\"QtdFaltas\":0},{\"DisciplinaNom\":\"QUI - QUÍMICA\",\"DisciplinaCod\":513,\"QtdFaltas\":0},{\"DisciplinaNom\":\"FIL - FILOSOFIA\",\"DisciplinaCod\":536,\"QtdFaltas\":0},{\"DisciplinaNom\":\"ATE - ARTE\",\"DisciplinaCod\":628,\"QtdFaltas\":0}]}]"}
```
</details>
