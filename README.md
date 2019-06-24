# Simple Google Sheet API Call
Simple cell's function to run an API call

Have to implement on 2 steps
1) Declare the google function on the file
2) Set a trigger to the function to refresh it's value
3) Implement on the Sheet

## 1) Set Function
a) Tools > Script Editor
![Screenshot](https://github.com/edulecca/googlesheetapicall/blob/master/scriptEditor.png)

b) paste the following script 

```
/**
 * @param String queryParamID get the cell´s value and pass by value to the function
 * @param String key, pass by value the key which json's value wants to be return
 */
function FUNCTION_NAME(queryParamID, key) {
  var url = "https://sampleurl.com/"+queryParamID;
  var response = UrlFetchApp.fetch(url);
  var data = response.getContentText();
  var json = JSON.parse(data);

 return json[key];
}
```

## 2) Set Trigger
a) Go to Edit > Set Trigger
![Screenshot](https://github.com/edulecca/googlesheetapicall/blob/master/activetrigger.png | width=200)

b) Add New Trigger
![Screenshot](https://github.com/edulecca/googlesheetapicall/blob/master/activador.png)

c) Set the refresh params as convenient (i.e. as open document)

## 3) Implement Function

a) set the function as **=FUNCTION_NAME(A2; 'status')**

b) function could be easily dragged to get dynamcally the Cell ID
