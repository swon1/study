# 📋 JavaScript - Time

### 🧷 JS 시간 관련된 코드들

<br><br>
#### 📌 시간 추출 ( 년/월/일/시/분/초 )
```Javascript
    let today = new Date();

    let year = today.getFullYear();
    let month = ('0' + (today.getMonth() + 1)).slice(-2);
    let day = ('0' + today.getDate()).slice(-2);
    let hour = ('0' + today.getHours()).slice(-2);
    let min = ('0' + today.getMinutes()).slice(-2);
    let sec = ('0' + today.getSeconds()).slice(-2);

    // 29990101246060
    let nowDate = parseInt(year+month+day+hour+min+sec);

    // 2999-01-31-24-60-60
    let dateString = year + '-' + month  + '-' + day + '-' + hour + '-' + min + '-' + sec;
```


<br><br>
