# Methods in Ruby

## Overview

In this lesson, we'll introduce methods, distinguish them from data types, and
cover how to create and execute them in your Ruby program.

You can follow along using IRB by typing `irb` in your terminal and copying the
provided code examples. Alternatively, in the `lib` folder, there is also a
file, `example.rb`, that you can use to copy the code examples into. You can run
this file from the lesson's main directory by typing `ruby lib/example.rb` to
see what it produces.

## Objectives

- Describe how methods can define new routines and procedures for our code.
- Define a method with the `def` keyword, supply the method's body, and close
  the method definition with the `end` keyword.
- Invoke a method by calling it by name.

### Why Use Methods

Methods define a new thing that your program can do. Variables are a mechanism
to teach your Ruby program about data; methods teach your Ruby program about a
new routine or behavior it can use. Variables are like nouns, methods are like
verbs.

For example, imagine needing to say "Hello World!" ten times. You might do something like this:
...............................................................................................
Nesta lição, vamos introduzir métodos, diferenciá-los dos tipos de dados e
cobre como criá-los e executá-los em seu programa Ruby.

Você pode acompanhar usando o IRB digitando `irb` em seu terminal e copiando o
exemplos de código fornecidos. Alternativamente, na pasta `lib`, há também um
arquivo, `example.rb`, que você pode usar para copiar os exemplos de código. Você pode correr
este arquivo do diretório principal da lição digitando `ruby lib/example.rb` para
veja o que produz.

## Objetivos

- Descrever como os métodos podem definir novas rotinas e procedimentos para o nosso código.
- Defina um método com a palavra-chave `def`, forneça o corpo do método e feche
  a definição do método com a palavra-chave `end`.
- Invoque um método chamando-o pelo nome.

### Por que usar métodos

Métodos definem uma coisa nova que seu programa pode fazer. As variáveis ​​são um mecanismo
para ensinar seu programa Ruby sobre dados; métodos ensinam seu programa Ruby sobre um
nova rotina ou comportamento que pode usar. Variáveis ​​são como substantivos, métodos são como
verbos.

```ruby
phrase = "Hello World!"
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
```

That works pretty well. You made use of a variable to encapsulate the data you
wanted to print and then the next ten lines literally print the phrase.

Now imagine later in your program you again want to say "Hello World!" ten
times. The entire program would look something like this:
...............................................................................................
Isso funciona muito bem. Você fez uso de uma variável para encapsular os dados que você
queria imprimir e, em seguida, as próximas dez linhas literalmente imprimem a frase.

Agora imagine que mais tarde em seu programa você queira dizer novamente "Hello World!" dez
vezes. O programa inteiro ficaria mais ou menos assim:

```ruby
phrase = "Hello World!"
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase

# ... The rest of the program

puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
```

We have to repeat the literal procedure for printing the value of `phrase` ten
times. If variables encapsulate and abstract data, methods encapsulate and
abstract procedure. Instead of literally `puts phrase` ten times, we can instead
build a method—a little machine that does exactly that whenever we want.

The method would look like this:
...............................................................................................
Temos que repetir o procedimento literal para imprimir o valor de `frase` dez
vezes. Se variáveis ​​encapsulam e abstraem dados, métodos encapsulam e
procedimento abstrato. Em vez de literalmente 'coloca a frase' dez vezes, podemos
construir um método - uma pequena máquina que faz exatamente isso sempre que queremos.

O método ficaria assim:

```ruby
def say_hello_world_ten_times
  phrase = "Hello World!"
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
end
```

Now, when we use the bareword `say_hello_world_ten_times` in our program, it
will invoke the method, running the code within the method. So the script above,
saying hello ten times, doing other things, then saying hello ten times again
could be rewritten as this:
...............................................................................................
Agora, quando usamos a palavra simples `say_hello_world_ten_times` em nosso programa,
invocará o método, executando o código dentro do método. Portanto, o script acima,
dizendo olá dez vezes, fazendo outras coisas, depois dizendo olá dez vezes novamente
poderia ser reescrito assim:

```ruby
def say_hello_world_ten_times
  phrase = "Hello World!"
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
end

say_hello_world_ten_times

# ... The rest of the program

say_hello_world_ten_times
```

That's way cleaner and follows the code principle "Don't Repeat Yourself" or
DRY. We abstract the action or procedure of putting "Hello World!" ten times
into a method. By defining the method  `say_hello_world_ten_times` once, we can
"call" or "invoke" the method as many times as we want in the future. Let's look
at methods in greater detail.

### Defining a Method

You can define a method in Ruby with the `def` keyword. A method's name can
begin with any lowercase letter. Here's a quick example:
...............................................................................................
Isso é muito mais limpo e segue o princípio do código "Don't Repeat Yourself" ou
SECO. Abstraímos a ação ou procedimento de colocar "Hello World!" dez vezes
em um método. Ao definir o método `say_hello_world_ten_times` uma vez, podemos
"chamar" ou "invocar" o método quantas vezes quisermos no futuro. Vamos olhar
em métodos em maior detalhe.

### Definindo um Método

Você pode definir um método em Ruby com a palavra-chave `def`. O nome de um método pode
comece com qualquer letra minúscula. Aqui está um exemplo rápido:

```ruby
def greeting # Method Signature
  puts "Hello World" # Method Body
end # Method Closing
```

**Note**: In the snippet above, we are using the `#` in a different way than
we've seen before. Here we are using it to put comments inside our code. Ruby
will see the `#` in the line of code (without the rest of the syntax required
for string interpolation) and will not interpret anything that follows. You can
use `#` in this way to add comments or clarifications to your code, either at
the end of a line of code as shown above or on a line by themselves. You can
also use it to "comment out" code (by putting `#` at the beginning of each line)
if you want to keep the code from executing temporarily. This can come in handy
during debugging.

The first line in the code snippet above, `def greeting`, is called the method
signature, it defines the basic properties of the method including the name of
the method, `greeting`.

Once you 'open' a method definition with the `def` keyword, all subsequent lines
in your program are considered the method's body, the actual procedure or code
that your method will run every time it's called.

You must terminate every opening `def` of a method with a corresponding `end` in
order to close the method body. If you don't correctly `end` a method, your
program will have unexpected results or break entirely because of a syntax
error. A good practice is to define the method and then immediately close it
before programming anything into the method.
...............................................................................................
**Observação**: no trecho acima, estamos usando o `#` de uma maneira diferente da
já vimos antes. Aqui estamos usando para colocar comentários dentro do nosso código. Rubi
iráver o `#` na linha de código (sem o resto da sintaxe necessária
para interpolação de string) e não interpretará nada que se segue. Você pode
use `#` desta forma para adicionar comentários ou esclarecimentos ao seu código, seja em
no final de uma linha de código, conforme mostrado acima, ou em uma linha isolada. Você pode
também use-o para "comentar" o código (colocando `#` no início de cada linha)
se você quiser impedir que o código seja executado temporariamente. Isso pode ser útil
durante a depuração.

A primeira linha no trecho de código acima, `def greeting`, é chamada de método
assinatura, define as propriedades básicas do método, incluindo o nome do
o método, `greeting`.

Depois de 'abrir' uma definição de método com a palavra-chave `def`, todas as linhas subseqüentes
em seu programa são considerados o corpo do método, o procedimento ou código real
que seu método será executado toda vez que for chamado.

Você deve terminar cada abertura `def` de um método com um `end` correspondente em
para fechar o corpo do método. Se você não `terminar` corretamente um método, seu
programa terá resultados inesperados ou quebrará totalmente por causa de uma sintaxe
erro. Uma boa prática é definir o método e fechá-lo imediatamente
antes de programar qualquer coisa no método.

```ruby
def greeting
  # Leave a line break for the method body
end # Immediately close the method.
```

Here we set up the method's structure first, ensuring a proper termination
before adding any other complexity.

> **Aside**: It's also a great practice to indent methods correctly. The body of
> a method should be indented two (2) spaces, placing it visually within the
> method. When you `end` the method, go back to the same indentation of the
> `def`, aligning the opening and closing of the method visually. Then you can
> easily define the body of the method and never worry about forgetting to `end`
> the method.
...............................................................................................
Aqui configuramos a estrutura do método primeiro, garantindo uma finalização adequada
antes de adicionar qualquer outra complexidade.

> **Aparte**: Também é uma ótima prática indentar os métodos corretamente. o corpo de
> um método deve ser recuado dois (2) espaços, colocando-o visualmente dentro do
> método. Quando você `end` o método, volte para o mesmo recuo do
> `def`, alinhando visualmente a abertura e fechamento do método. Então você pode
> defina facilmente o corpo do método e nunca se preocupe em esquecer de `end`
> o método.

```ruby
def greeting
  puts "Hello World" # Now code the body of the method.
end
```

### Invoking a Method

Once you define a method, you can execute the method whenever you want by using
the method name in your code.
...............................................................................................
Depois de definir um método, você pode executá-lo quando quiser usando
o nome do método em seu código.

```ruby
def greeting
  puts "Hello World"
end

greeting # Executing the method by name
#=> "Hello World"

greeting # Executing the method again
#=> "Hello World"
```

> **Note**: If you have been using IRB so far, exit out of it before continuing.
> The remaining portion of this lesson involves bash commands you will need to
> enter into the terminal.

Let's try making a method we can use over and over. Make a new file called
`greeting.rb` (you can use: `touch greeting.rb` from your terminal). Put the
following code in it:
................................................................................................
> **Nota**: Se você estiver usando o IRB até agora, saia dele antes de continuar.
> A parte restante desta lição envolve comandos bash que você precisará
> entre no terminal.

Vamos tentar criar um método que possamos usar repetidamente. Crie um novo arquivo chamado
`greeting.rb` (você pode usar: `touch greeting.rb` do seu terminal). Coloque o
seguinte código nele:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```bash
$ ruby greeting.rb
$
```

You'll notice that when you run your program, nothing happens. Your program
successfully defined the method but it never executed it. Just because you built
a machine doesn't mean that you turned it on. Update your `greeting.rb` to
entirely read:
................................................................................................
Você notará que, ao executar seu programa, nada acontece. seu programa
definiu o método com sucesso, mas nunca o executou. Só porque você construiu
uma máquina não significa que você a ligou. Atualize seu `greeting.rb` para
totalmente lido:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end

greeting
```

Save your file and run it with `ruby greeting.rb`. You'll see:
................................................................................................
Salve seu arquivo e execute-o com `ruby greeting.rb`. Você vai ver:
```bash
$ ruby greeting.rb
Hello World
$
```

Now your program actually executed the program. Update the code again to
entirely read:
................................................................................................
Agora seu programa realmente executou o programa. Atualize o código novamente para
totalmente lido:
File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end

greeting
greeting
greeting
greeting
greeting
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```bash
$ ruby greeting.rb
Hello World
Hello World
Hello World
Hello World
Hello World
$
```

The bareword `greeting` will execute the body of the defined method.

#### Writing Code vs Reading About Code

Let's end by talking briefly about one additional use of `#`. Programmers love
conventions, or agreed upon rules that help them talk to each other about code.
A common syntax convention for Ruby methods is to preface them with a `#`, and
in subsequent lessons, you might see method names written with a `#` in front of
them. For example, if a method is named 'greeting', rubyists will often refer to 
it as `#greeting`. This is so that other rubyists can instantly recognize it as 
a method, as opposed to a variable or a bareword or a class. But remember that 
when you write it in your code, it should be `greeting` and not `#greeting`.
................................................................................................
Vamos terminar falando brevemente sobre um uso adicional de `#`. Os programadores adoram
convenções ou regras acordadas que os ajudam a conversar uns com os outros sobre código.
Uma convenção de sintaxe comum para métodos Ruby é prefaciá-los com um `#`, e
nas lições subseqüentes, você pode ver os nomes dos métodos escritos com um `#` na frente de
eles. Por exemplo, se um método é chamado de 'saudação', os rubistas geralmente se referem a
como `#saudação`. Isso é para que outros rubiistas possam reconhecê-lo instantaneamente como
um método, em oposição a uma variável ou uma palavra simples ou uma classe. Mas lembre-se disso
quando você escreve em seu código, deve ser `greeting` e não `#greeting`.
