Guia de Estilo de Código
========================

Este guia estende e expande a [PSR-1](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md), os padrões básicos de codificação.

A intenção deste guia é reduzir a fricção cognitiva durante a codificação de diferentes autores enumerando um conjunto compartilhado de regras e expectativas sobre como formatar um código PHP.

As regras de estilo daqui são derivadas de semelhanças entre vários projetos de membros. Quando vários autores colaboram através de vários projetos, isso ajuda a ter um conjunto de diretrizes para ser usado em todos esses projetos. Assim, o benefício deste guia não está nas regras em si, mas no compartilhamento dessas regras.

As palavras-chave "DEVE(M)" (must, required, shall), "NÃO DEVE(M)" (must not, shall not), "DEVERIA(M)" (should, recommended), "NÃO DEVERIA(M)" (should not), "PODE(M)" (may) e "OPCIONAL" (optional) nesse documento devem ser interpretadas como descrito na [RFC 2119](http://www.ietf.org/rfc/rfc2119.txt).

1. Visão Geral
--------------

- O código DEVE usar 4 espaços para indentação ao invés de tabs.

- NÃO DEVE haver um limite rigoroso (hard limit) no comprimento das linhas; o limite suave (soft limit) DEVE ser de 120 caracteres; linhas DEVERIAM ser de 80 caracteres ou menos.

- DEVE haver uma linha em branco após a declaração do `namespace` e DEVE haver uma linha em branco após o bloco de declarações `use`.

- A abertura de chaves para classes DEVE estar na próxima linha e o fechamento na próxima linha DEVE estar na próxima linha após o corpo.

- A abertura de chaves para métodos DEVE estar na próxima linha e o fechamento na próxima linha DEVE estar na próxima linha após o corpo.

- A visibilidade DEVE ser declarada em todas as propriedades e métodos; as palavras-chave `abstract` e `final` DEVEM ser declaradas antes da visibilidade; a palavra-chave `static` DEVE ser declarada após a visibilidade.

- As palavras-chave de estruturas de controle DEVEM ter um espaço depois delas; chamadas de métodos e funções NÃO DEVEM.

- A abertura de chaves para estruturas de controle DEVE estar na mesma linha e o fechamento DEVE estar na próxima linha após o corpo.

- A abertura de parênteses para estruturas de controle NÃO DEVE ter um espaço depois dela e o fechamento de parênteses para estruturas de controle NÃO DEVE ter um espaco antes.

### 1.1. Exemplo

Este exemplo engloba algumas das regras abaixo como uma visão geral:

```php
<?php
namespace Vendor\Package;

use FooInterface;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class Foo extends Bar implements FooInterface
{
    public function sampleFunction($a, $b = null)
    {
        if ($a === $b) {
            bar();
        } elseif ($a > $b) {
            $foo->bar($arg1);
        } else {
            BazClass::bar($arg2, $arg3);
        }
    }

    final public static function bar()
    {
        // corpo do método
    }
}
```

2. Geral
--------

### 2.1 Padrão Básico de Codificação

O código DEVE seguir todas as regras descritas na [PSR-1](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md).

### 2.2 Arquivos

Todos os arquivos PHP DEVEM usar o fim da linha Unix LF (linefeed).

Todos os arquivos PHP DEVEM terminar com uma única linha em branco.

A tag de fechamento `?>` DEVE ser omitida em arquivos que contêm somente PHP.

### 2.3. Linhas

NÃO DEVE haver um limite rigoroso (hard limit) no comprimento das linhas.

O limite suave (soft limit) DEVE ser de 120 caracteres; verificadores de estilo automatizados DEVEM avisar mas NÃO DEVEM assinalar como erro no limite suave (soft limit).

As linhas NÃO DEVERIAM ser maiores do que 80 caracteres; as linhas mais longas que isso DEVERIAM ser quebradas em várias linhas subsequentes com não mais de 80 caracteres cada.

NÃO DEVE haver espaço em branco no final de linhas não-em-branco.

As linhas em branco PODEM ser adcionadas para aumentar a legibilidade e para indicar blocos de código relacionados.

NÃO DEVE haver mais de um comando (statement) por linha.

### 2.4. Indentação

O código DEVE usar uma indentação de 4 espaços e NÃO DEVE usar tabs para indentação.

> Note bem: Usando apenas espaços e não misturando espaços com tabs ajuda a evitar
> problemas com diffs, patches, history e annotations. O uso de espaços
> também torna mais fácil inserir sub-indentação refinada para alinhamento na entrelinha.

### 2.5. Palavras-chave e True/False/Null

[Palavras-chave](http://php.net/manual/en/reserved.keywords.php) do PHP DEVEM ser em letra minúscula (lower case).

As constantes do PHP `true`, `false` e `null` DEVEM ser em letra minúscula (lower case).

3. Namespace e Declarações de 'use'
-----------------------------------

Quando presente, DEVE haver uma linha em branco depois da declaração de `namespace`.

Quando presentes, todas as declarações `use` DEVEM vir depois da declaração de `namespace`.

DEVE haver uma palavra-chave `use` para cada declaração.

DEVE haver uma linha em branco após o bloco `use`.

Por exemplo:

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

// ... código PHP adicional ...

```

4. Classes, Propriedades e Métodos
----------------------------------

O termo "classe" é uma referência a todas as classes, interfaces e traits.

### 4.1. Extends e Implements

As palavras-chave `extends` e `implements` DEVEM ser declaradas na mesma linha do nome da classe.

A chave de abertura para a classe DEVE estar em sua própria linha; a chave de fechamento para a classe DEVE estar na linha seguinte depois do corpo.

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // constantes, propriedades e métodos
}
```

Listas de `implements` PODEM ser dividas em múltiplas linhas, onde cada linha subsequente é indentada uma vez. Quando fizer isto, o primeiro item na lista DEVE estar na próxima linha e DEVE haver uma interface por linha.

```php
<?php
namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    // constantes, propriedades e métodos
}
```

### 4.2. Propriedades

A visibilidade DEVE ser declarada em todas as propriedades.

A palavra-chave `var` NÃO DEVE ser utilizada para declarar uma propriedade.

NÃO DEVE haver mais de uma propriedade declarada por instrução.

Os nomes das propriedades NÃO DEVERIAM ser prefixados com um único underscore para indicar a visibilidade protegida ou privada.

Uma declaração de propriedade se parece com o seguinte:

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public $foo = null;
}
```

### 4.3. Métodos

A visibilidade DEVE ser declarada em todos os métodos.

Os nomes de métodos NÃO DEVERIAM ser prefixados com um único undersocre para indicar visibilidade protegida ou privada.

Os nomes de métodos NÃO DEVEM ser declarados com um espaço após ao nome do método. A chave de abertura DEVE estar em sua própria linha e a chave de fechamento DEVE estar na linha seguinte ao fechamento do corpo. NÃO DEVE haver um espaço depois do parêntese de abertura e NÃO DEVE haver um espaço antes do parêntese de fechamento.

Uma declaração de método se parece com o seguinte. Note a colocação dos parênteses, vírgulas, espaços e chaves:

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
    {
        // corpo do método
    }
}
```

### 4.4. Argumentos de Métodos

Na lista de argumentos, NÃO DEVE haver um espaço antes de cada vírgula e DEVE haver um espaço após cada vírgula.

Os argumentos de métodos com valores padrão DEVEM vir no final da lista de argumentos.

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function foo($arg1, &$arg2, $arg3 = [])
    {
        // corpo do método
    }
}
```

As listas de argumento PODEM ser dividas em múltiplas linhas, onde cada linha subsequente é indentada uma vez. Quando fizer isto, o primeiro item na lista DEVE estar na próxima linha e DEVE haver um argumento por linha.

Quando a lista de argumento for dividida em múltiplas linhas, o parêntese de fechamento e a chave de abertura DEVEM ser colocados na mesma linha com um espaço entre eles.

```php
<?php
namespace Vendor\Package;

class ClassName
{
    public function umNomeDeMetodoMuitoLongo(
        ClassTypeHint $arg1,
        &$arg2,
        array $arg3 = []
    ) {
        // corpo do método
    }
}
```

### 4.5. `abstract`, `final` e `static`

Quando presentes, as declarações `abstract` e `final` DEVEM preceder a declaração de visibilidade.

Quando presente, a declaração `static` DEVE vir depois da declaração de visibilidade.

```php
<?php
namespace Vendor\Package;

abstract class ClassName
{
    protected static $foo;

    abstract protected function zim();

    final public static function bar()
    {
        // corpo do método
    }
}
```

### 4.6. Métodos e Chamadas de Função

Ao fazer um método ou chamada de função, NÃO DEVE haver um espaço entre o método ou o nome da função e o parêntese de abertura, NÃO DEVE haver um espaço depois do parêntese de abertura e NÃO DEVE haver um espaço antes do parêntese de fechamento. Na lista de argumento, NÃO DEVE haver um espaço antes de cada vírgula e DEVE haver um espaço depois de cada vírgula.

```php
<?php
bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
```
As listas de argumento PODEM ser dividas em múltiplas linhas, onde cada linha subsequente é indentada uma vez. Quando fizer isto, o primeiro item na lista DEVE estar na próxima linha e DEVE haver um argumento por linha.

```php
<?php
$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
```

5. Estruturas de Controle
-------------------------

As regras gerais de estilo para estruturas de controle são as seguintes:

- DEVE haver um espaço depois da palavra-chave da estrutura de controle
- NÃO DEVE haver espaço depois do parêntese de abertura
- NÃO DEVE haver espaço depois do parêntese de fechamento
- DEVE haver um espaço entre o parêntese de fechamento e a chave de abertura
- A estrutura do corpo DEVE ser indentada uma vez
- A chave de fechamento DEVE vir na próxima linha após o corpo

O corpo de cada estrutura DEVE ser delimitado por chaves. Isso padroniza como as estruturas se parecem e reduz a probabilidade de introdução de erros à medida em que novas linhas vão sendo adicionadas ao corpo.

### 5.1. `if`, `elseif`, `else`

Uma estrutura `if` se parece com o seguinte. Note a posição dos parênteses, espaços e chaves; e que `else` e `elseif` são na mesma linha da chave de fechamento do corpo anterior.

```php
<?php
if ($expr1) {
    // corpo if
} elseif ($expr2) {
    // corpo elseif
} else {
    // corpo else;
}
```
A palavra-chave `elseif` DEVERIA ser usada ao invés de `else if`, de modo que todas as estruturas de controle pareçam uma única palavra.

### 5.2. `switch`, `case`

Uma estrutura `switch` se parece com o seguinte. Note a posição dos parênteses, espaços e chaves. A declaração `case` DEVE ser indentada uma vez do `switch` e a palavra-chave `break` (ou outra palavra-chave de finalização) DEVE ser indentada no mesmo nível do corpo de `case`. DEVE haver um comentário como `// no break` quando é intencional cair ("fall-through") num `case` com corpo não-vazio.

```php
<?php
switch ($expr) {
    case 0:
        echo 'Primeiro caso, com uma quebra';
        break;
    case 1:
        echo 'Segundo caso, que "cai" para o(s) seguinte(s)';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Terceiro caso, return é usado ao invés de break';
        return;
    default:
        echo 'Caso padrão';
        break;
}
```


### 5.3. `while`, `do while`

Uma estrutura `while` se parece com o seguinte. Note a posição dos parênteses, espaços e chaves.

```php
<?php
while ($expr) {
    // corpo de estrutura
}
```

Igualmente, uma estrutura `do while` se parece com o seguinte. Note a posição dos parênteses, espaços e chaves.

```php
<?php
do {
    // corpo de estrutura;
} while ($expr);
```

### 5.4. `for`

Uma estrutura `for` se parece com o seguinte. Note a posição dos parênteses, espaços e chaves.

```php
<?php
for ($i = 0; $i < 10; $i++) {
    // corpo de for
}
```

### 5.5. `foreach`

Uma estrutura `foreach` se parece com o seguinte. Note a posição dos parênteses, espaços e chaves.

```php
<?php
foreach ($iterable as $key => $value) {
    // corpo de foreach
}
```

### 5.6. `try`, `catch`

Um bloco `try catch` se parece com o seguinte. Note a posição dos parênteses, espaços e chaves.

```php
<?php
try {
    // corpo de try
} catch (FirstExceptionType $e) {
    // corpo de catch
} catch (OtherExceptionType $e) {
    // corpo de catch
}
```

6. Closures
-----------

As closures DEVEM ser declaradas com um espaço depois da palavra-chave `function` e um espaço antes e depois da palavra-chave `use`.

A chave de abertura DEVE vir na mesma linha e a chave de fechamento DEVE vir na próxima linha após o corpo.

NÃO DEVE haver um espaço após o parêntese de abertura de uma lista de argumentos ou lista de variáveis e NÃO DEVE haver um espaço antes do parêntese de fechamento da lista de argumentos ou lista de variáveis.

Na lista de argumentos e na lista de variáveis, NÃO DEVE haver um espaço antes de cada vírgula e DEVE haver um espaço depois de cada vírgula.

Os argumentos de closure com valores padrão DEVEM vir depois da lista de argumentos.

Uma declaração de closure se parece com o seguinte. Note a posição de parênteses, vírgulas, espaços e chaves:

```php
<?php
$closureWithArgs = function ($arg1, $arg2) {
    // corpo
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // corpo
};
```

As listas de argumento e listas de variáveis PODEM ser divididas em múltiplas linhas, onde cada linha subsequente é indentada uma vez. Quando fizer isso, o primeiro item na lista DEVE estar na próxima linha e DEVE haver um argumento ou variável por linha.

Quando a lista de argumento ou lista de variáveis forem dividida em múltiplas linhas, o parêntese de fechamento e a chave de abertura DEVEM ser colocados na mesma linha com um espaço entre eles.

Os seguintes são exemplos de closures com e sem listas de argumentos e variáveis divididas em múltiplas linhas.

```php
<?php
$longArgs_noVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) {
   // corpo
};

$noArgs_longVars = function () use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // corpo
};

$longArgs_longVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // corpo
};

$longArgs_shortVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use ($var1) {
   // corpo
};

$shortArgs_longVars = function ($arg) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // corpo
};
```

Note que as regras de formatação também se aplicam quando a closure é usada diretamente em uma chamada de função ou método como um argumento.

```php
<?php
$foo->bar(
    $arg1,
    function ($arg2) use ($var1) {
        // corpo
    },
    $arg3
);
```

7. Conclusão
------------

Há muitos elementos de estilo e práticas intencionalmente omitidos por este guia. Estes incluem, mas não estão limitados a:

- Declaração de variáveis globais e constantes globais

- Declaração de funções

- Operadores e atribuição

- Alinhamento entrelinhas

- Comentários e blocos de documentação

- Prefixos e sufixos de nome de classe

- Melhores práticas

Recomendações futuras PODEM revisar e estender este guia para abordar esses ou outros elementos de estilo e prática.