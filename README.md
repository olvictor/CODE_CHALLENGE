## <center> Desáfios de Lógica. </center>

🧩Desafio: Primeira Letra Única


Dada uma string, encontre o primeiro caractere que não se repete e retorne-o. Se todos os caracteres se repetem, retorne null.

🔸 Entrada:

> "abaccdeff"

🔹 Saída esperada:

> "b"

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
