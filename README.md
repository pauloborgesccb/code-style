Padrão de Desenvolvimento de Código
==================

Objetivo: Criar  uma  padronização de código para utilizar no code review tornando mais fácil o desenvolvimento e futuras manutenções.

Metas e objetivos: 

•	Ter um padrão de código para fazer um code review com qualidade.
•	Manutenção e a evolução de código mais fácil.

O padrão de código  a seguir se basea no **PSR-2**.


1. Nomenclaturas
--------

Além do **PSR-2** algumas nomenclaturas para o nome de arquivos também foram pensadas:

### 2.1 Module
O nome de um Module deve ter referencia ao objetivo do modulo que deseja criar, utilizando a lingua portuguesa no padrão de UpperCamelCase. 
O Module deve ser criado no diretorio referente ao projeto, caso seja um module comum a todos (uteis da vida) deve se encontrar dentro do diretorio "Application".
```
Ex. Quero criar um module de padrão de codigo, o nome dele ficaria CodigoPadraoModule
```

### 2.2 Controller
O nome da controller devem fazer referencia ao contexto de suas ações.
O nome de uma controller deve seguir o padrão UpperCamelCase e deve estar em português. 
```
Ex. Para a controller de crud o nome dela ficaria CodigoPadraoController.php
```

### 2.3 Services
O nome do serviço deve fazer referencia ao contexto de suas ações.
O nome do serviço deve seguir o padrão UpperCamelCase e deve estar em português e sufixado por Service.
```
Ex. Para a minha Service de listagem de padrão de código o nome seria CodigoPadraoService.php
```

### 2.4 Entity
As entidades devem ter o nome de acordo com o nome da tabela que ela descreve.
O nome da entidade deve seguir o padrão UpperCamelCase e deve estar em português e sufixado por Entity.
As PKs devem ser alteradas de "id" para o padrão já utilizado hoje co_nome_tabela
```
Ex. A tabela da entidade CodigoPadraoEntity.php seria tb_codigo_padrao e para a PK ficaria co_codigo_padrao.
```

### 2.5 Repository
Os repositórios devem ter o nome de acordo com a entidade que ele corresponde. 
O nome do repositório deve seguir o padrão UpperCamelCase e deve estar em português e sufixado por Repository.
```
Ex. O repositorio da entidade CodigoPadraoEntity.php seria CodigoPadraoRepository.php
```

### 2.6 Form
O nome de um form deve representar a ação que vai ser realizada nele.
O nome de um form deve seguir o padrão lowerCamelCase e deve estar em português e sufixado por Form.
```
Ex. O form do cadastro do padrão de código seria CodigoPadraoCadastroForm.php
```

### 2.7 JS
O nome do JS deve fazer referencia a view que ele vai ser utilizado ou a ação que ele vai executar quando utilizado.
O nome do JS deve seguir o padrão lowerCamelCase e deve estar em português.
```
Ex. O JS da lista de gerenciamente do padrão de código seria CodigoPadraoCadastro.js
``` 

### 2.8 CSS
O nome do CSS deve fazer referencia ao seu objetivo.
O nome do CSS deve seguir o padrão lowerCamelCase e deve estar em português.
```
Ex. O CSS da lista de gerenciamente do padrão de código seria CodigoPadraoCadastro.css
```

2. Configurando o phpValidator
--------

> 1.1. Fazer checkout do projeto [Coding-Style-GUIDE](https://url)

> 1.2. Importar no Intellij o arquivo [settings.jar](https://url/settings.jar) 

> 1.3. Ir em configurações do Intellij selecionar a opção PHP e configurar o php instalado na sua maquina.

> 1.4 Caso utilize Windows você precisa acessar os arquivos phpmd/phpmd/src/phpmd.bat e squizlabs/php_codesniffer/scripts/phpcs.bat para configurar o caminho do PHP instalado na sua maquina. O valor padrão de instalação do PHP é "C:\php\php.exe".

> 1.5. Selecionar Mess Detector dentro da opção PHP para configurar o phpmd, vá para a pasta  *phpValidator e selecione o arquivo  phpmd/phpmd/src/phpmd.php no caso de Linux e OSX phpmd/phpmd/src/phpmd.bat

> 1.6. Selecionar Code Sniffer dentro da opção PHP e configurar o phpcs, vá para a pasta *phpValidator e selecione o arquivo  squizlabs/php_codesniffer/scripts/phpcs no caso de Linux e OSX squizlabs/php_codesniffer/scripts/phpcs.bat

> 1.7. No menu de configurações do Intellij acesse Inspections, encontre "PHP" na lista de scope e habilite as opções de "PHP Code Sniffer validation" e "PHP Mess Detector validation"

> 1.8. No menu do Intellij vá em File e selecione a opção "Invalidate Caches / Restart..." escolha a opção "Invalidate and Restart" e assim que o seu Intellij terminar de reiniciar estará com o padrão de código todo configurado e pronto para ser usado.

