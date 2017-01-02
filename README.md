# Alert
Diretiva para emitir alertas

##Instalação
---------
Inclua os arquivos abaixo na sua página

```html
<!-- Alert -->
<link href="<%=ResolveUrl("~/")%>UAUComponente/diretivas/Alerta/AlertaStyle.css" rel="stylesheet" />
<script src="<%=ResolveUrl("~/")%>UAUComponente/diretivas/Alerta/AlertaDirective.js"></script>
```

Adicione a dependência ao módulo
```javascript
var myApp = angular.module('app',['UAUAlerta'])
```

Adicione a diretiva na pagina, posicionando onde os alertas devem ser exibidos, é recomendado que seja no topo da pagina
```html
<aleta></alerta>
```

Injetar o serviço alertaService em qual quer lugar onde for necessário emitir alerta.
```javascript
myApp.controller('myController', function ($scope, alertaService) {
    $scope.addAlert = function () {
        alertaService.add("danger","Alguma coisa aconteceu!");
    };
});
```
API
---------
+ **Alerting Factory**
  + `addAlert(type, message)`

    Add an alert of the given type to the list with the given message. Will apply the class `.alert-[type]` to the alert.
  + `addInfo(message)`

