### install to project
```bash
git clone git@github.com:Tsukugi/ACR-NFC-Reader-PhoneGap-Plugin.git
cordova plugin add ../ACR-NFC-Reader-PhoneGap-Plugin/
```

### Usage

#### ACR.onReady

This method will be invoke when Reader ready.

__Example__

```javascript
  ACR.onReady = function (reader) {
     alert("ready " + reader);
  }
```

#### ACR.addTagListener

Registers an event listener for Reader, retrieves Object with Tag data.

```javascript
  ACR.addTagListener(success,failure);
```

__Parameters__

 - `success`: on detect a chip successful;
 - `failure`: on detect a chip failure;

__Example__

```javascript
  ACR.addTagListener(
      function(result){
        alert(JSON.stringify(result));
      },
      function(result){
        alert(JSON.stringify(result));
      }
  );
```

#### ACR.readData

Read data from chip

```javascript
  ACR.readData(block,success,failure);
```

__Parameters__

 - `block`: which block you want to read.
 - `success`: successful callback;
 - `failure`: failure callback;

__Example__

```javascript
  ACR.readData(4,
      function(result){
        alert("Data: " + JSON.stringify(result));
      },
      function(result){
        alert("Data Failure: " + JSON.stringify(result));
      }
  );
```
#### ACR.writeData

write data to chip, maximum 16 character in each block

```javascript
  ACR.writeData(block,data,success,failure);
```

__Parameters__

 - `block`: which block you want to write.
 - `data`:  the data will be write to chip.
 - `success`: successful callback;
 - `failure`: failure callback;

__Example__

```javascript
  ACR.writeData(4,
      "test",
      function(result){
        alert("Write Data: " + JSON.stringify(result));
      },
      function(result){
        alert("Write Data Failure: " + JSON.stringify(result));
      }
  );
```
