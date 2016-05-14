
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

`$ ./sencha app build ios AMBIENTE_DESEJADO(development, staging ou production)`
```
    > O arquivo será gerado no caminho:
     `./cordova/platforms/android/build/outputs/apk/android-debug.apk`

    > Para instalar no dispositivo rode:
    `$ adb install -r ./cordova/platforms/android/build/outputs/apk/android-debug.apk`
```

####IOS :feelsgood:

`$ ./sencha app build ios env AMBIENTE_DESEJADO(development, staging ou production)`
```
```

####Windows Phone :finnadie:

`$ sencha config prop envAMBIENTE_DESEJADO(development, staging ou production) then app build wp8`
```
```


