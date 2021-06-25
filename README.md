# Export an Embedded HTML Table to CSV | Excel

1. Right-click on the bookmark's bar in your browser > Select "Add Page..."

2. Enter a name for the bookmark "Name". Then copy/paste the following in the "URL" section: 

    ```javascript
    javascript:void%20function(){function%20getJavaScript(url,success){var%20script=document.createElement(%22script%22);script.src=url;var%20head=document.getElementsByTagName(%22head%22)[0],done=!1;script.onload=script.onreadystatechange=function(){done||this.readyState%26%26%22loaded%22!=this.readyState%26%26%22complete%22!=this.readyState||(done=!0,success(),script.onload=script.onreadystatechange=null,head.removeChild(script))},head.appendChild(script)}function%20addCSVLinks(){jQuery(%22.csvLink%22).remove(),jQuery(%22table%22).each(function(index){jQuery(this).attr(%22data-csvtable%22,index).before('%3Ca%20href=%22%23%22%20class=%22csvLink%22%20data-forcsvtable=%22'+index+'%22%3EExport%20to%20CSV%3C/a%3E')}),jQuery(%22.csvLink%22).click(function(){var%20text=%22%22,csvTableIndex=jQuery(this).attr(%22data-forcsvtable%22);jQuery('table[data-csvtable=%22'+csvTableIndex+'%22]%20tr').each(function(){jQuery(%22td,%20th%22,this).each(function(index){0!=index%26%26(text+=%22,%22),text+='%22'+formatedText(jQuery(this).html())+'%22'}),text+=%22\r\n%22}),jQuery(%22.csvLink%22).remove(),downloadCSVFile(%22TableExport.csv%22,%22text/csv%22,text)})}function%20formatedText(html){var%20ret=html;return%20ret=ret.replace(/\n/g,%22%20%22),ret=ret.replace(/\t/g,%22%20%22),ret=ret.replace(/\s+/g,%22%20%22),ret=decodeHtml(ret),ret=ret.replace(/%3Cbr%3E/gi,%22\n%3Cbr%3E%22),ret=ret.replace(/%3Cbr/gi,%22\n%3Cbr%20%22),ret=ret.replace(/%3Cp/gi,%22\n%3Cp%20%22),ret=ret.replace(/%22/gi,'%22%22'),ret=ret.replace(/^\n/,%22%22),ret=ret.replace(/(%3C([^%3E]+)%3E)/gi,%22%22)}function%20decodeHtml(html){var%20txt=document.createElement(%22textarea%22);return%20txt.innerHTML=html,txt.value}function%20downloadCSVFile(filename,mime,text){if(window.navigator.msSaveOrOpenBlob){var%20blob=new%20Blob([decodeURIComponent(encodeURI(text))],{type:%22text/csv;charset=utf-8%22});window.navigator.msSaveBlob(blob,filename)}else{var%20pom=document.createElement(%22a%22);pom.setAttribute(%22href%22,%22data:%22+mime+%22;charset=utf-8,%22+encodeURIComponent(text)),pom.setAttribute(%22download%22,filename),document.body.appendChild(pom),pom.click(),document.body.removeChild(pom)}}%22undefined%22==typeof%20jQuery%3FgetJavaScript(%22//code.jquery.com/jquery-latest.min.js%22,function(){addCSVLinks()}):addCSVLinks()}();
    ```

3. When you see a table on a browser that you want to export, click on the saved bookmark. You should see the words `Export to CSV` appear on the upper left-hand corner of the table:

    ![](/assets/html-table.png) 

4. Click on the button and you should be good to go!
   
    [](/assets/oxutput-table.png) 