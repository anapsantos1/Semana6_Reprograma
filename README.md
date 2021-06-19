# Sexta semana de aula na Reprograma 🚀

Turma Online 12 - Todas em Tech | Back-end | 2021 | Introdução à API:
HTTP e NodeJS

Aluna: Ana Paula Araujo

## Exercício da semana
1) Qual a relação entre os métodos HTTP e o CRUD? 

CRUD é um acrônimo de c-create, r-read, u-update, d-delete essas são as 4 operações básicas.

Os métodos HTTP parecem estar diretamente ligado com o CRUD:
Create -> POST.
Read -> GET.
Update -> PUT / PATCH.
Delete -> DELETE.



2) Comente, com exemplos, a diferença entre o PUT e o PATCH.

Definição:

os métodos HTTP PUT e PATCH são usados para indicar uma requisição de alteração de dados.

Na documentação esses dois métodos são muito parecido, uma diferença é o PUT deve passar todos os dados do recurso preenchidos independente se você editou somente um item. ex:. você criou uma classe nota que tem os atributos titulo e descrição, você editou o título. Na documentação indica que você precisa passar os dois atributos preenchidos para o serviço do PUT.

O PATCH foi criado para eliminar essa necessidade de enviar todos os atributos – o consumidor envia apenas aquilo que de fato foi alterado (mais o ID como parâmetro, para que o serviço saiba o que vai ser alterado).



3) Assim como na aula, apresente os dados dos JSONs no console 

   - No colors-rgb.js apresente o nome da cor e o codigo RGB como no exemplo: "gainsboro - rgb(220, 220, 220, 1)"

        

        Para esse exercício utilizei o método For ...in:

        O laço **`for...in`** interage sobre propriedades enumeradas de um objeto, na ordem original de inserção. O laço pode ser executado para cada propriedade distinta do objeto.  [Fonte: Mozilla](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for...in)

        ```
        let resultado = obj[0];
        
        for (let prop in resultado) {
        
                console.log("Nomes da cor: " + prop + " - rgb " + "(" + resultado[prop] + ")");
              }
        ```

        

   - No estados-cidade.js apresente o nome do Estado, a sigla e todas as cidadades, sem arrays aparentes no console

        

        Para resolver esse utilizei método forEach():

        O método `forEach()` executa uma dada função em cada elemento de um array.

        [Fonte: Mozilla](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)

        ```
        let brasil = data[0]
        let estados = brasil.estados
        
        estados.forEach(estado => { 
        
          console.log("Nome do estado: " + estado.nome 
            + " Sigla: " +  estado.sigla + " Cidades: ") 
            
            estado.cidades.forEach(cidade => {
              console.log(cidade)
            })
          console.log(" ")
        });
        ```

        

   - No filmes.js apresente titulo, plot, generos e lingua. Genero e lingua devem ser apresentados em arrays no console.

        

        Utilizei novamente o forEach() e o Split:

        O método `split()` divide uma String em uma lista ordenada de substrings, coloca essas substrings em um array e retorna o array. A divisão é feita procurando um padrão, onde o padrão é fornecido como o primeiro parâmetro na chamada do método. [Fonte: Mozilla](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/String/split)

        ```
        let filmes = obj
        
        
        filmes.forEach(filme => {
        
        
            console.log(" Titulo : " + filme.Title + " Plot : " + filme.Plot )
            console.log("Gênero: ", filme.Genre.split(","));
            console.log("Língua: ", filme.Language.split(","),"\n");
        
        });
        ```

        

4) Defina o conceito de idempotência e como uma API pode ser idempotente

definição de idempotente no dicionário:

Que tem a propriedade de poder ser aplicado mais do que uma vez sem que o resultado se altere (ex.: matriz idempotente, operação idempotente).

Conceito de idempotência conforme o site: [`Developer.Mozilla`](https://developer.mozilla.org/pt-BR/docs/Glossary/Idempotent) :

Um método HTTP é **idempotente** se uma requisição idêntica pode ser feita uma ou mais vezes em sequência com o mesmo efeito enquanto deixa o servidor no mesmo estado. Em outras palavras, um método idempotente não deveria possuir nenhum efeito colateral (exceto para manter estatísticas). Implementados corretamente, o GET , HEAD, PUT, e DELETE são métodos **idempotentes**, mas não o método POST. Todos os métodos seguros também são idempotentes.

Para ser idempotente, somente o estado atual do *back-end* de um servidor deve ser considerado, o código de status retornado por cada requisição pode variar: a primeira chamada de um DELETE vai provavelmente retornar um 200, enquanto as chamadas sucessivas vão provavelmente retornar 404. Outra implicação do DELETE ser idempotente é de que os desenvolvedores não deveriam implementar APIs RESTful com a funcionalidade de deleção de última entrada usando o método `DELETE`.

Note que a idempotência de um método não é garantida pelo servidor, algumas aplicações também podem quebrar a constante de idempotência.

5) Cite alguns diferentes padrões de projetos de software

Fábrica, Singleton, Proxy, Adaptador, Fachada, Decorador, Strategy, Observador, Template Method e Visitor.

