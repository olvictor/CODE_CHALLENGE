## <center> Desáfios de Lógica. </center>

🧩Desafio: Primeira Letra Única


Dada uma string, encontre o primeiro caractere que não se repete e retorne-o. Se todos os caracteres se repetem, retorne null.

🔸 Entrada:

> "abaccdeff"

🔹 Saída esperada:

> "b"

## Resolução:

> const entrada ="abaccdeff"
> let encontrou = false;
> const mapeamentoDeLetras = new Map();
> for(let letra of entrada){
>&nbsp;&nbsp;if(mapeamentoDeLetras.has(letra)){
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mapeamentoDeLetras.set(letra, mapeamentoDeLetras.get(letra) + 1);
    }else{
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; mapeamentoDeLetras.set(letra,1)
 &nbsp;&nbsp;}
>}
>for(const [letra,contagem] of mapeamentoDeLetras){
&nbsp;&nbsp;if(contagem == 1){
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      console.log(letra)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      encontrou = true;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       break;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    }else{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return null
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    }
>}
>if (!encontrou) return null;
