## javasctipt

--- 

- <script>
```
    // html
    <script>

    </script>

    // xhtml
    <script><![CDATA[
        // javascript code
    ]]></script>
```

```
    // 显示时间
    function displayTime() {
        var elt = document.getElementById("clock");
        var now = new Date();
        elt.innerHTML = now.toLocaleTimeString();   // "下午3:43:56"
        setTimeout(displayTime, 1000);
    }
    window.onload = displayTime;
```