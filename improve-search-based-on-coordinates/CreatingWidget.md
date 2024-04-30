Steps

- Arrastar a pasta `client` do web app builder para vscode  
- Abra a pasta ==stemapp== => ==widgets==: criei uma pasta com o nome desejado da widget  
  
- Abra a documentação:  
  
- Dentro da pasta, crie um Json chamado manifest.json, com o conteúdo widget manifest da documentação: [https://developers.arcgis.com/web-appbuilder/guide/widget-manifest.htm](https://developers.arcgis.com/web-appbuilder/guide/widget-manifest.htm)  
- Confira e cole no arquivo, veja se é este código :  
```
{  
"name": "NomeDoWidget",  
"platform": "HTML",  
"version": "2.11",  
"wabVersion": "2.11",  
}  
```
  
- Adicione o parâmetro propriedades:  
```
{  
"name": "SmartCoodinates",  
"platform": "HTML",  
"version": "2.11",  
"wabVersion": "2.11",  
"properties": { <= desta forma  
"hasLocale": false,  
"hasStyle": false,  
"hasConfig": false,  
"hasSettingPage": false  
}  
}  
```
  
- Feito isso, crie outro arquivo agora um `Widget.js` e inclua o script da documentação que está logo abaixo no menu "extend baseWidget", e pra teste um console.log, cole o código no arquivo pelo `vscode` ou outro.
- Exemplo: 


```
define(['dojo/_base/declare', 'jimu/BaseWidget'], function(declare, BaseWidget) { //To create a widget, you need to derive from BaseWidget. return declare([BaseWidget], { // DemoWidget code goes here
	console.log("Start up bro!")
}); });
```


Veja também o `widget life cycle` no mesmo menu da documentação.

- Agora crie o arquivo de html `Widget.html` e insira somente div em sua estrutura, pois será o conteúdo que aparecerá dentro da widget.


- Dentro da pasta ==sample-configs==  copie o arquivo ==config-demo.json==  e cole dentro da pasta ==config==, renomeie e abra no navegador com a seguinte URL  

> [! .../webappbuilder/stemapp/?config=configs/arquivo-renomeado.json]

- Irá abrir um mapa e no canto superior direito, confirmando este passo, edite o arquivo após.
- Dentro do arquivo já renomeado altere os parâmetros:

  [Exemplo do arquivo config-demo.json ]


   
```
{
  "theme": {
    "name": "FoldableTheme"
  },
  
  "portalUrl": "http://www.arcgis.com",
  "appId":"",
  "title": "ArcGIS Web Application - Demo Widgets",
  "subtitle": "with ArcGIS Web AppBuilder",
  "geometryService": "http://tasks.arcgisonline.com/ArcGIS/rest/services/Geometry/GeometryServer",

  "links":[
    {
      "label": "ArcGIS Online"
    }
  ],

  "widgetOnScreen": {
    "widgets": [{
      "uri": "themes/FoldableTheme/widgets/HeaderController/Widget",
      "positionRelativeTo": "browser",
      "position": {
        "left": 0,
        "top": 0,
        "right": 0,
        "height": 45
      }
    }]
  },
  
  "map": {
    "3D": false,
    "2D": true,
    "itemId": "141f8f1a43a8405993e08264836a207b",
    "position": {
      "left": 0,
      "top": 45,
      "right": 0,
      "bottom": 0
    }
  },
  "widgetPool": {
    "panel": {
      "uri": "themes/FoldableTheme/panels/FoldablePanel/Panel",
      "positionRelativeTo": "map",
      "position": {
        "top": 1,
        "right": 1,
        "bottom": 1
      }
    },
    
    "widgets": [{
      "label": "SmartCoodinates",
      "uri": "widgets/SmartCoodinates/Widget"
    }]
  }
}
```

- Remova as seguintes linhas incluindo a vírgula: 
```
   {
      "uri": "widgets/samplewidgets/WidgetCommunication/WidgetA/Widget",
      "position": {
        "left": 45,
        "top": 45
      }
    }, {
      "uri": "widgets/Select/Widget",
      "position": {
        "left": 95,
        "top": 45
      }
    }
```

- Na parte de widget dentro do arquivo, exclua todas as propriedades e relacione sua widget passando os parâmetros:
```
"widgets": [{
      "label": "SmartCoodinates",    => nome que aparecerá no rótulo
      "uri": "widgets/SmartCoodinates/Widget"  => endereço da widget na estrutura de pastas
    }]
```

	- Depois execute um console.log na widget.js e observar no console do navegador;
	- e pronto! só abrir o navegador e dar continuidade com propriedades e                                         implementação da widget.