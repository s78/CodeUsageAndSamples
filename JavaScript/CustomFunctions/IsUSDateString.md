## isUSDateString

``` javascript
function isUSDateString(value) {
    var len = value.length;
    if (len < 8 || 10 < len) {
        return false;
    }
  
    var parts = value.split('/').map(function (s) { return parseInt(s); });
  
    if (parts.length != 3) {
        return false;
    }
  
    var year = parts[2];
    var month = parts[0] - 1;
    var day = parts[1];

    return (1970 <= year && year <= 2500 && 1 <= month && month <= 12 && 1 <= day && day <= 31);
}
```
