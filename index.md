![haha](https://www.infoescola.com/wp-content/uploads/2009/12/bandeira-de-santa-catarina.jpg)

### Point

<code>
http://estudantesc.sc.gov.br/ws/
</code>

### Pegar dados do aluno

Dados necessários: Matricula, Data de nascimento;
```php
http://estudantesc.sc.gov.br/ws/get_dados_aluno.php?matricula=MATRICULA&datanas=DATA DE NASCIMENTO
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_dados_aluno.php?matricula=237590466&datanas=12042000
```

Retorno:

```javascript
[{"AlunoNom":"NOME COMPLETO","UeCod":CÓDIGO,"UeNom":"ESCOLA","UeEnd":"RUA","UeNumEnd":NUMERO,"UeMunNom":"CIDADE"}]
```

### Pegar boletim do aluno

Dados necessários: Matricula;
```php
http://estudantesc.sc.gov.br/ws/get_boletim_geral.php?matricula=MATRICULA
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_boletim_geral.php?matricula=237590466
```

Retorno:

```javascript
[{"DisciplinaNome":"BIOLOGIA","Nota1":0,"Falta1":0,"Nota2":0,"Falta2":0,"Nota3":0,"Falta3":0,"Nota4":0,"Falta4":0,"NotaExame":0,"NotaRecuperacao":0,"NotaFinal":0}]
//OPS: sai uma linha dessa para cada materia
```

### Pegar grade do aluno

Dados necessários: Matricula;
```php
http://estudantesc.sc.gov.br/ws/get_grade_aluno.php?matricula=MATRICULA
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_grade_aluno.php?matricula=237590466
```

Retorno:

```javascript
[{"Cd":"255","Nm":"BIL - BIOLOGIA"},{"Cd":"301","Nm":"MAT - MATEMÁTICA"},{"Cd":"302","Nm":"GEO - GEOGRAFIA"},{"Cd":"304","Nm":"HIS - HISTÓRIA"},{"Cd":"307","Nm":"EFI - EDUCAÇÃO FÍSICA"},{"Cd":"319","Nm":"LEI - LÍNGUA ESTRANGEIRA - INGLÊS"},{"Cd":"401","Nm":"LPL - LÍNGUA PORTUGUESA E LITERATURA"},{"Cd":"437","Nm":"SOC - SOCIOLOGIA"},{"Cd":"475","Nm":"FIS - FÍSICA"},{"Cd":"513","Nm":"QUI - QUÍMICA"},{"Cd":"536","Nm":"FIL - FILOSOFIA"},{"Cd":"628","Nm":"ATE - ARTE"}]
```

### Pegar a nota do aluno

Dados necessários: Matricula, Código da materia (Retornado na Grade);
```php
http://estudantesc.sc.gov.br/ws/get_notas.php?matricula=MATRICULA&disc=CÓDIGO
// Exemplo:
http://estudantesc.sc.gov.br/ws/get_notas.php?matricula=237590466&disc=319
```

Retorno:

```javascript
{"DisciplinaNom":"LÍNGUA ESTRANGEIRA - INGLÊS","NotaWS":[{"AtividadesBimestre":1,"AtividadesCod":101,"AtividadesDescricao":"TB1","AtividadesData":"2019-03-15T00:00:00","TiposAtividadeDescricao":"Trabalho","AtividadeNota":9.5000}]}
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
curl_setopt($ch, CURLOPT_URL, 'http://estudantesc.sc.gov.br/ws/{{ API_CALL }}');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
$data = curl_exec($ch);
curl_close($ch); 
$result = json_decode($data, true);
```


### Exemplo com  e XMLHttpRequest

```javascript
var xhttp = new XMLHttpRequest();
xhttp.open("GET","https://estudantesc.sc.gov.br/ws/{{ API_CALL }}", true);
xhttp.send();
var rt = xhttp.responseText;
```
