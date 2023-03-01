## JavaScript - 事件(Event)对象深入

#### addEventListener 添加事件监听
+ 不会被覆盖

Example:
```
<body>
    <input type="button" name="" value="add" id="ipt">

    <!-- JavaScript -->
    <script>
        /*
        // 如果重新赋值的话，之前的值会被覆盖
        ipt.onclick = function(){
            alert(1);
        }

        ipt.onclick = function(){
            alert(2);
        }
        // 弹出 2
        */
        
        // 不会被覆盖
        ipt.addEventListener('click',function(){
            alert(3);
        });
        ipt.addEventListener('click',function(){
            alert(4);
        });
        // 3 和 4 都有弹出

    </script>
</body>
```























