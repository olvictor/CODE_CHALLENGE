## <center> Desáfios de Lógica. </center>

🧩Desafio: Primeira Letra Única

QUESTÂO 1 -
Dada uma string, encontre o primeiro caractere que não se repete e retorne-o. Se todos os caracteres se repetem, retorne null.

🔸 Entrada:

``` "abaccdeff"```

🔹 Saída esperada:

``` "b" ```

## Resolução:

```javascript

const entrada = "abaccdeff";
let encontrou = false;
const mapeamentoDeLetras = new Map();

for (let letra of entrada) {
    if (mapeamentoDeLetras.has(letra)) {
        mapeamentoDeLetras.set(letra, mapeamentoDeLetras.get(letra) + 1);
    } else {
        mapeamentoDeLetras.set(letra, 1);
    }
}

for (const [letra, contagem] of mapeamentoDeLetras) {
    if (contagem == 1) {
        console.log(letra);
        encontrou = true;
        break;
    } else {
        return null;
    }
}

if (!encontrou) return null;
```
🧩 Desafio: Agrupar Anagramas

QUESTÂO 2 - 
Dada uma lista de palavras, agrupe todas que são anagramas umas das outras. A ordem das palavras dentro dos grupos não importa, mas os grupos devem estar organizados em um array.

🔸 Entrada:

``` ["bat", "tab", "tap", "pat", "cat"]```

🔹 Saída esperada:

``` > [["bat", "tab"], ["tap", "pat"], ["cat"]]```

## Resolução:

```javascript

const entrada = ["bat", "tab", "tap", "pat", "cat"];

const mapeamentoPalavras = new Map();

for (const palavra of entrada) {
    const chave = palavra.split("").sort().join("");
  
    if (mapeamentoPalavras.has(chave)) {
      mapeamentoPalavras.get(chave).push(palavra);
    } else {
      mapeamentoPalavras.set(chave, [palavra]);
    }
}
const resultado = Array.from(mapeamentoPalavras.values())
console.log(resultado)
```
