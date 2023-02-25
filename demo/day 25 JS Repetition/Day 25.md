## JavaScript 的逻辑判断语句

### 1.0 for 循环
+ for(var i = 0;i<allDiv.length;i++){}

##### 1.0.1 continue
+ 跳过当前循环，但是接下去的循环照常进行

Example:
```
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>

    <!-- JavaScript -->
    <script>
        var allDiv = document.getElementsByTagName('div');

        for(var i = 0;i<allDiv.length;i++){
            if(i == 2){
                continue;   // 跳过当前循环
            }
            allDiv[i].style.background = 'red';
        }

    </script>

</body>
```
> + continue - 跳过当前循环
> + 条件语句(if-else) - 可以在 for 循环里面使用


##### 1.0.2 mod
+ 符号: %
+ 通常用来做检测偶数与奇数的条件语句
> + if(i % 2 == 0){}  // 偶数 even
> + if(i % 2 != 0){}  // 奇数 odd

Example:
```
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>7</div>
    <div>8</div>
    <div>9</div>
    <div>10</div>

    <!-- JavaScript -->
    <script>
        var allDiv = document.getElementsByTagName('div');

        for(var i = 0;i<allDiv.length;i++){
            // 使偶数的 i 的颜色保持不变
            if(i % 2 == 0){
                continue;   // 跳过当前循环
            }
            allDiv[i].style.background = 'red';
        }

    </script>

</body>
```

##### 1.0.3 break
+ 可以设立一些条件，并中断循环，且强制使其循环结束/中断运行
+ 不会影响到之前运行过的代码的结果
+ 只会阻止代码原本过后要运行的行动，使其没有运行成功
+ 比如，要从 a 去到 e，但是设立在 c 的时候中断了，所以系统只运行到 a，b 和 c，但是c 过后的也就是 d 和 e 并不会实行

Example:
```
<body>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>7</div>
    <div>8</div>
    <div>9</div>
    <div>10</div>

    <!-- JavaScript -->
    <script>
        var allDiv = document.getElementsByTagName('div');

        for(var i = 0;i<allDiv.length;i++){
            // 当 i 相等于 2 的时候，循环中断
            if(i == 2){
                break;
            }
            allDiv[i].style.background = 'red';
        }

    </script>

</body>
```
