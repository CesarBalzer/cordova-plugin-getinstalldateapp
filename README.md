# Cordova pegar data/hora de instalação e data/hora de atualização do APP

Plugin simples para pegar a data de instalação e data de atualização do app, com base da captura de data de instalação do aplicativo via Java.

## Como utilizar

Crie um novo projeto Cordova:

    $ cordova create gdia br.com.example Gdia
    
Instalando o plugin, entre no diretorio:

    $ cd gdia
    $ cordova plugin add https://github.com/CesarBalzer/cordova-plugin-getdateinstallapp.git
    

Edite seu arquivo `www/js/index.js` e adicione o seguinte código para pegar a data de instalação, depois da função de chamada `app.initialize()`

```js
	document.getElementById("getDateTime").addEventListener("click", getDataInstalacao);
	function getDataInstalacao() {
    	var sucesso = function (mensagem) {
        	alert(mensagem);
    }

    var falha = function () {
        alert("Erro na chamada do plugin");
    }

    Gdia.getdatetime("br.com.example", sucesso, falha);
}
```
Ou para pegar a data de atualização do app

```js
	document.getElementById("getUpdateTime").addEventListener("click", getDataAtualizacao);
	function getDataAtualizacao() {
    var success = function (message) {
        alert(message);
    }

    var failure = function () {
        alert("Error calling Gdia Plugin");
    }

    Gdia.getupdatetime("br.com.example", success, failure);
}
```
Instale a plataforma Android

    cordova platform add android
    
Execute seu código

    cordova run 

## Mais Informações

Para mais informações de como configurar o Apache Cordova acesse a documentação[the documentation](http://cordova.apache.org/docs/en/latest/guide/cli/index.html)

Para mais informações dos plugins acesse [Plugin Development Guide](http://cordova.apache.org/docs/en/latest/guide/hybrid/plugins/index.html)
