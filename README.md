# google-app-script
Cheatsheet of Google App Script Formulas

**Display a List of Sheet Names**

Use this to create an index sheet with a list sheet names. You'll need to copy paste values if you want to edit the list

```javascript
function sheetnames() {
  var out = new Array()
  var sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  for (var i=0 ; i<sheets.length ; i++) out.push( [ sheets[i].getName() ] )
  return out 
}

```

**Count Rows in Sheet**

Use this to create an index sheet with a list sheet names. You'll need to copy paste values if you want to edit the list
```javascript
=counta(indirect(concatenate(A2,"!A:A")))
```

**Instagram Hashtags**

To count the number of posts per hashtag, use this
```javascript
=IF(ISNUMBER(SEARCH("k",REGEXEXTRACT(IMPORTXML(A7,"//meta[@name='description']/@content"),"(.{1,})(?: Posts)"))),SUBSTITUTE(REGEXEXTRACT(IMPORTXML(A7,"//meta[@name='description']/@content"),"(.{1,})(?: Posts)"),"k","")*1000,IF(ISNUMBER(SEARCH("m",REGEXEXTRACT(IMPORTXML(A7,"//meta[@name='description']/@content"),"(.{1,})(?: Posts)"))),SUBSTITUTE(REGEXEXTRACT(IMPORTXML(A7,"//meta[@name='description']/@content"),"(.{1,})(?: Posts)"),"m","")*1000000,REGEXEXTRACT(IMPORTXML(A7,"//meta[@name='description']/@content"),"(.{1,})(?: Posts)")*1))

```
