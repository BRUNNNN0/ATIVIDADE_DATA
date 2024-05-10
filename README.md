ATIVIDADE DATAS JS<br/>

Realizamos esta atividade com o intuito de entender mais sobre os usos da datas:<br/>

nesta atividades criamos 3 funcões, vou explicar cada uma:<br/>

na função compararData ele pega as duas variaveis do tipo "Date" fornecidas pela pagina inicial do HTML
e utiliaza um if para realizar as comparação do "data1.getTime" e o "data2.getTime" e ver se a data1 é maior 
que a data2 ou se elas são iguais<br/>
function compararData(data1, data2) {<br/>
    if (data1.getTime() > data2.getTime()) {<br/>
        return converterData(data1);<br/>
    }<br/>
    else if (data1.getTime() == data2.getTime()) {<br/>
        let igual = "As datas estão iguais";<br/>
        return igual;<br/>
    }<br/>
    return converterData(data2);<br/>
}<br/>

na função intervaloData ele pega as duas variaveis do tipo "Date" fornecidas pela pagina inicial do HTML
e utiliaza um if para realizar as comparação do "data1.getTime" e o "data2.getTime"
porem nesta comparação ele verifica se a primeira data é maior que a segunda e a codição sendo atendida,
Ele pega a variavel "data1.getTime" faz menos "data2.getTime" o resultado é dividido por mil para converter 
milissegundos para segundos e retornar o espaço entre os dias corretamente.<br/>
function intervaloData(data1, data2) {<br/>
    if (data1.getTime() >= data2.getTime()) {<br/>
        alert("Primeira data deve ser mais antiga!");<br/>
        return false;<br/>
    }<br/>
    return (data2.getTime() - data1.getTime()) / 1000;<br/>
}<br/>

E por ultimo temos a função para converterData, essa função ira receber a variavel "dataAtual" que é um objeto do tipo "Date", 
ele pega a varivel e separa os elementos em hora minuto etc... ,  abre diversos ifs para realizar verificações para checar se os campos tem a 
quantidade correta de caracteres, caso não tenha é adicionado um zero, assim fazendo o retorno da variavel "novaData" em String de acordo com oque foi solicitado no pdf!.<br/>
function converterData(dataAtual) {<br/>
    let ano = (dataAtual.getFullYear()).toString();<br/>
    let mes = (dataAtual.getMonth() + 1).toString();<br/>
    let dia = (dataAtual.getDate()).toString();<br/>
    let horas = (dataAtual.getHours()).toString();<br/>
    let minutos = (dataAtual.getMinutes()).toString();<br/>
    console.log(mes.length);<br/>
    if (mes.length < 2) {<br/>
        mes = "0" + mes;<br/>
    }<br/>
    if (dia.length < 2) {<br/>
        dia = "0" + dia;<br/>
    }<br/>
    if (horas.length < 2) {<br/>
        horas = "0" + horas;<br/>
    }<br/>
    if (minutos.length < 2) {<br/>
        minutos = "0" + minutos;<br/>
    }<br/>
    let novaData = `${horas}:${minutos} - ${dia}/${mes}/${ano}`;<br/>
    return novaData;<br/>
}<br/>

