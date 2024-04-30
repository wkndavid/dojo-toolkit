==Warnings==

 _addWarning: function () {
 
        popupAlert = new Popup({
          class:"popupAlert",
          titleLabel: 'MANUTENÇÃO EM BANCO DE DADOS',
          customZIndex: 2000,
          width: 310,
          height: 205,
          content: 'Serviço temporariamente indisponível! Estamos realizando uma manutenção no banco de dados. Por favor, tente novamente mais tarde!',
          buttons :[{label: 'OK',  onClick: lang.hitch(this, function(evt) {popupAlert.close(evt);  loading.hide();})}]
        });
        // aqui termina a função de _addWarning();
        if (query(".attwarning", this.attrInspector.domNode).length === 0) {
          var txt = domConstruct.create("div", { 'class': 'attwarning' });
          txt.innerHTML = this.nls.attachmentSaveDeleteWarning;
          if (this.attrInspector._attachmentEditor !== undefined &&
            this.attrInspector._attachmentEditor !== null) {
            this.attrInspector._attachmentEditor.domNode.appendChild(txt);
          }
        }
      },

comentado:
//_popupAlert = new Popup ({
 
                    //class:"popupAlert",
                   //titleLabel: 'MANUTENÇÃO EM BANCO DE DADOS',
                  //customZIndex: 2000,
                   //width: 310,
                   // height: 205,
                   // content: 'Serviço temporariamente indisponível! Estamos realizando uma manutenção no banco de dados. Por favor, tente novamente mais tarde!',
                   // buttons :[{
                   // label: 'OK',
                   // onClick: lang.hitch(this, function(evt) {
                   // popupAlert.close(evt);  
                   // loading.hide();
                   //})                  
                 //}]
               //});





















[[obsidian://open?vault=Obsidian%20Vault&file=Widgets%2FCreatingWidget.pdf]]
[[CreatingWidget]]