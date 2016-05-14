
##Iniciando projeto :sunglasses:

###Linux :penguin: / MAC :apple:

`$ ./sencha app init`


###Windows :bomb:

`$ npm install`

`$ node_modules/.bin/bower install`


##Iniciando mock :shipit:

`$ ./sencha mock init`


##Alterações no SASS em tempo real :bowtie:

`$ ./sencha app watch`


##Compilar SASS :bowtie:

`$ ./sencha ant sass`


##Vefificação de código, complexidade, estilo, padrões e linhas duplicadas :mag:

`$ node_modules/.bin/gulp lint`

`$ node_modules/.bin/gulp cs`

`$ node_modules/.bin/gulp cpd`


##Build's :nut_and_bolt:

####Android :hurtrealbad:
```
###Gerando apk
$ ./sencha app build ios AMBIENTE_DESEJADO(development, staging ou production)`
###O arquivo será gerado no caminho:
    "./cordova/platforms/android/build/outputs/apk/android-debug.apk"
###Para instalar no dispositivo rode:
$ adb install -r ./cordova/platforms/android/build/outputs/apk/android-debug.apk
```

####IOS :feelsgood:

```
###Criando Projeto para XCode
$ ./sencha app build ios env AMBIENTE_DESEJADO(development, staging ou production)
###Abra o projeto localizado em:
"./cordova/platforms/ios/NOME_DO_PROJETO.xcodeproj"

###Na barra superior à esquerda, selecione o dispositivo
###Na barra superior à esquerda, clique no play :arrow_forward:, para instalar no dispositivo.
```

####Windows Phone :finnadie:

```
#Criando Projeto para VisualStudio
$ sencha config prop envAMBIENTE_DESEJADO(development, staging ou production) then app build wp8
###Abra o projeto localizado em:
"./cordova/platforms/wp8/"

###Na barra superior à esquerda, selecione no play :arrow_forward: a opção device
###Na barra superior à esquerda, clique no play :arrow_forward:, para instalar no dispositivo.
```

