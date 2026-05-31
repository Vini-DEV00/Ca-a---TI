<script lang="ts">
   let palavra = ""
   let selecionadas: string[]=[]
   const palavrasValidas = ["PYTHON", "GO", "PHP", "JAVASCRIPT", "KOTLIN", "DART", "HTML", "CSS", "JAVA", "SVELTE"]
   
   function selecionar (id: string, letra: string){
    if(!selecionadas.includes(id)){
        selecionadas = [...selecionadas, id];
        palavra += letra;
    }
   }
   function verificar () {
    if(palavrasValidas.includes(palavra)) {
        alert('você encontrou a palavra ' + palavra) 
    }else{
        alert('palavra errada, seu lixo')
    } 
    palavra = "";
    selecionadas = [];
   }
   
</script>

<h1>DESCUBRA AS PALAVRAS DO PROGRAMADOR</h1>

<table>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('00')} on:click={() => selecionar('00','J')}>J</td>
        <td class="cell" class:selected={selecionadas.includes('01')} on:click={() => selecionar('01','Q')}>Q</td>
        <td class="cell" class:selected={selecionadas.includes('02')} on:click={() => selecionar('02','Q')}>Q</td>
        <td class="cell" class:selected={selecionadas.includes('03')} on:click={() => selecionar('03','X')}>X</td>
        <td class="cell" class:selected={selecionadas.includes('04')} on:click={() => selecionar('04','O')}>O</td>
        <td class="cell" class:selected={selecionadas.includes('05')} on:click={() => selecionar('05','K')}>K</td>
        <td class="cell" class:selected={selecionadas.includes('06')} on:click={() => selecionar('06','E')}>E</td>
        <td class="cell" class:selected={selecionadas.includes('07')} on:click={() => selecionar('07','K')}>K</td>
        <td class="cell" class:selected={selecionadas.includes('08')} on:click={() => selecionar('08','E')}>E</td>
        <td class="cell" class:selected={selecionadas.includes('09')} on:click={() => selecionar('09','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('010')} on:click={() => selecionar('010','H')}>H</td>
        <td class="cell" class:selected={selecionadas.includes('011')} on:click={() => selecionar('011','P')}>P</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('10')} on:click={() => selecionar('10','A')}>A</td>
        <td class="cell" class:selected={selecionadas.includes('11')} on:click={() => selecionar('11','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('12')} on:click={() => selecionar('12','Y')}>Y</td>
        <td class="cell" class:selected={selecionadas.includes('13')} on:click={() => selecionar('13','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('14')} on:click={() => selecionar('14','H')}>H</td>
        <td class="cell" class:selected={selecionadas.includes('15')} on:click={() => selecionar('15','O')}>O</td>
        <td class="cell" class:selected={selecionadas.includes('16')} on:click={() => selecionar('16','N')}>N</td>
        <td class="cell" class:selected={selecionadas.includes('17')} on:click={() => selecionar('17','W')}>W</td>
        <td class="cell" class:selected={selecionadas.includes('18')} on:click={() => selecionar('18','V')}>V</td>
        <td class="cell" class:selected={selecionadas.includes('19')} on:click={() => selecionar('19','C')}>C</td>
        <td class="cell" class:selected={selecionadas.includes('110')} on:click={() => selecionar('110','C')}>C</td>
        <td class="cell" class:selected={selecionadas.includes('111')} on:click={() => selecionar('111','H')}>H</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('20')} on:click={() => selecionar('20','V')}>V</td>
        <td class="cell" class:selected={selecionadas.includes('21')} on:click={() => selecionar('21','A')}>A</td>
        <td class="cell" class:selected={selecionadas.includes('22')} on:click={() => selecionar('22','A')}>A</td>
        <td class="cell" class:selected={selecionadas.includes('23')} on:click={() => selecionar('23','M')}>M</td>
        <td class="cell" class:selected={selecionadas.includes('24')} on:click={() => selecionar('24','I')}>I</td>
        <td class="cell" class:selected={selecionadas.includes('25')} on:click={() => selecionar('25','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('26')} on:click={() => selecionar('26','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('27')} on:click={() => selecionar('27','K')}>K</td>
        <td class="cell" class:selected={selecionadas.includes('28')} on:click={() => selecionar('28','H')}>H</td>
        <td class="cell" class:selected={selecionadas.includes('29')} on:click={() => selecionar('29','Ç')}>Ç</td>
        <td class="cell" class:selected={selecionadas.includes('210')} on:click={() => selecionar('210','S')}>S</td>
        <td class="cell" class:selected={selecionadas.includes('211')} on:click={() => selecionar('211','T')}>T</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('30')} on:click={() => selecionar('30','A')}>A</td>
        <td class="cell" class:selected={selecionadas.includes('31')} on:click={() => selecionar('31','R')}>R</td>
        <td class="cell" class:selected={selecionadas.includes('32')} on:click={() => selecionar('32','W')}>W</td>
        <td class="cell" class:selected={selecionadas.includes('33')} on:click={() => selecionar('33','V')}>V</td>
        <td class="cell" class:selected={selecionadas.includes('34')} on:click={() => selecionar('34','C')}>C</td>
        <td class="cell" class:selected={selecionadas.includes('35')} on:click={() => selecionar('35','L')}>L</td>
        <td class="cell" class:selected={selecionadas.includes('36')} on:click={() => selecionar('36','S')}>S</td>
        <td class="cell" class:selected={selecionadas.includes('37')} on:click={() => selecionar('37','B')}>B</td>
        <td class="cell" class:selected={selecionadas.includes('38')} on:click={() => selecionar('38','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('39')} on:click={() => selecionar('39','M')}>M</td>
        <td class="cell" class:selected={selecionadas.includes('310')} on:click={() => selecionar('310','S')}>S</td>
        <td class="cell" class:selected={selecionadas.includes('311')} on:click={() => selecionar('311','D')}>D</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('40')} on:click={() => selecionar('40','S')}>S</td>
        <td class="cell" class:selected={selecionadas.includes('41')} on:click={() => selecionar('41','X')}>X</td>
        <td class="cell" class:selected={selecionadas.includes('42')} on:click={() => selecionar('42','S')}>S</td>
        <td class="cell" class:selected={selecionadas.includes('43')} on:click={() => selecionar('43','H')}>H</td>
        <td class="cell" class:selected={selecionadas.includes('44')} on:click={() => selecionar('44','M')}>M</td>
        <td class="cell" class:selected={selecionadas.includes('45')} on:click={() => selecionar('45','I')}>I</td>
        <td class="cell" class:selected={selecionadas.includes('46')} on:click={() => selecionar('46','J')}>J</td>
        <td class="cell" class:selected={selecionadas.includes('47')} on:click={() => selecionar('47','O')}>O</td>
        <td class="cell" class:selected={selecionadas.includes('48')} on:click={() => selecionar('48','I')}>I</td>
        <td class="cell" class:selected={selecionadas.includes('49')} on:click={() => selecionar('49','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('410')} on:click={() => selecionar('410','Z')}>Z</td>
        <td class="cell" class:selected={selecionadas.includes('411')} on:click={() => selecionar('411','M')}>M</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('50')} on:click={() => selecionar('50','C')}>C</td>
        <td class="cell" class:selected={selecionadas.includes('51')} on:click={() => selecionar('51','Ç')}>Ç</td>
        <td class="cell" class:selected={selecionadas.includes('52')} on:click={() => selecionar('52','V')}>V</td>
        <td class="cell" class:selected={selecionadas.includes('53')} on:click={() => selecionar('53','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('54')} on:click={() => selecionar('54','U')}>U</td>
        <td class="cell" class:selected={selecionadas.includes('55')} on:click={() => selecionar('55','N')}>N</td>
        <td class="cell" class:selected={selecionadas.includes('56')} on:click={() => selecionar('56','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('57')} on:click={() => selecionar('57','J')}>J</td>
        <td class="cell" class:selected={selecionadas.includes('58')} on:click={() => selecionar('58','A')}>A</td>
        <td class="cell" class:selected={selecionadas.includes('59')} on:click={() => selecionar('59','L')}>L</td>
        <td class="cell" class:selected={selecionadas.includes('510')} on:click={() => selecionar('510','H')}>H</td>
        <td class="cell" class:selected={selecionadas.includes('511')} on:click={() => selecionar('511','P')}>P</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('60')} on:click={() => selecionar('60','R')}>R</td>
        <td class="cell" class:selected={selecionadas.includes('61')} on:click={() => selecionar('61','Y')}>Y</td>
        <td class="cell" class:selected={selecionadas.includes('62')} on:click={() => selecionar('62','E')}>E</td>
        <td class="cell" class:selected={selecionadas.includes('63')} on:click={() => selecionar('63','M')}>M</td>
        <td class="cell" class:selected={selecionadas.includes('64')} on:click={() => selecionar('64','R')}>R</td>
        <td class="cell" class:selected={selecionadas.includes('65')} on:click={() => selecionar('65','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('66')} on:click={() => selecionar('66','D')}>D</td>
        <td class="cell" class:selected={selecionadas.includes('67')} on:click={() => selecionar('67','R')}>R</td>
        <td class="cell" class:selected={selecionadas.includes('68')} on:click={() => selecionar('68','O')}>O</td>
        <td class="cell" class:selected={selecionadas.includes('69')} on:click={() => selecionar('69','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('610')} on:click={() => selecionar('610','V')}>V</td>
        <td class="cell" class:selected={selecionadas.includes('611')} on:click={() => selecionar('611','J')}>J</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('70')} on:click={() => selecionar('70','I')}>I</td>
        <td class="cell" class:selected={selecionadas.includes('71')} on:click={() => selecionar('71','X')}>X</td>
        <td class="cell" class:selected={selecionadas.includes('72')} on:click={() => selecionar('72','L')}>L</td>
        <td class="cell" class:selected={selecionadas.includes('73')} on:click={() => selecionar('73','L')}>L</td>
        <td class="cell" class:selected={selecionadas.includes('74')} on:click={() => selecionar('74','F')}>F</td>
        <td class="cell" class:selected={selecionadas.includes('75')} on:click={() => selecionar('75','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('76')} on:click={() => selecionar('76','R')}>R</td>
        <td class="cell" class:selected={selecionadas.includes('77')} on:click={() => selecionar('77','D')}>D</td>
        <td class="cell" class:selected={selecionadas.includes('78')} on:click={() => selecionar('78','A')}>A</td>
        <td class="cell" class:selected={selecionadas.includes('79')} on:click={() => selecionar('79','R')}>R</td>
        <td class="cell" class:selected={selecionadas.includes('710')} on:click={() => selecionar('710','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('711')} on:click={() => selecionar('711','A')}>A</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('80')} on:click={() => selecionar('80','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('81')} on:click={() => selecionar('81','M')}>M</td>
        <td class="cell" class:selected={selecionadas.includes('82')} on:click={() => selecionar('82','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('83')} on:click={() => selecionar('83','U')}>U</td>
        <td class="cell" class:selected={selecionadas.includes('84')} on:click={() => selecionar('84','Q')}>Q</td>
        <td class="cell" class:selected={selecionadas.includes('85')} on:click={() => selecionar('85','S')}>S</td>
        <td class="cell" class:selected={selecionadas.includes('86')} on:click={() => selecionar('86','X')}>X</td>
        <td class="cell" class:selected={selecionadas.includes('87')} on:click={() => selecionar('87','B')}>B</td>
        <td class="cell" class:selected={selecionadas.includes('88')} on:click={() => selecionar('88','Ç')}>Ç</td>
        <td class="cell" class:selected={selecionadas.includes('89')} on:click={() => selecionar('89','K')}>K</td>
        <td class="cell" class:selected={selecionadas.includes('810')} on:click={() => selecionar('810','X')}>X</td>
        <td class="cell" class:selected={selecionadas.includes('811')} on:click={() => selecionar('811','V')}>V</td>
    </tr>
    <tr>
        <td class="cell" class:selected={selecionadas.includes('90')} on:click={() => selecionar('90','T')}>T</td>
        <td class="cell" class:selected={selecionadas.includes('91')} on:click={() => selecionar('91','X')}>X</td>
        <td class="cell" class:selected={selecionadas.includes('92')} on:click={() => selecionar('92','E')}>E</td>
        <td class="cell" class:selected={selecionadas.includes('93')} on:click={() => selecionar('93','O')}>O</td>
        <td class="cell" class:selected={selecionadas.includes('94')} on:click={() => selecionar('94','G')}>G</td>
        <td class="cell" class:selected={selecionadas.includes('95')} on:click={() => selecionar('95','O')}>O</td>
        <td class="cell" class:selected={selecionadas.includes('96')} on:click={() => selecionar('96','G')}>G</td>
        <td class="cell" class:selected={selecionadas.includes('97')} on:click={() => selecionar('97','Y')}>Y</td>
        <td class="cell" class:selected={selecionadas.includes('98')} on:click={() => selecionar('98','I')}>I</td>
        <td class="cell" class:selected={selecionadas.includes('99')} on:click={() => selecionar('99','W')}>W</td>
        <td class="cell" class:selected={selecionadas.includes('910')} on:click={() => selecionar('910','P')}>P</td>
        <td class="cell" class:selected={selecionadas.includes('911')} on:click={() => selecionar('911','A')}>A</td>
    </tr>
</table>

<p> palavra atual: {palavra} </p>
<button on:click = {verificar}>
verificar palavra
</button>


<a class="menu" href="/">Voltar ao Menu</a>