## JavaScript 循环

#### for 循环
+ for(初始的条件;判断条件;循环){}

Example:
```
<script>

/*
    for(var i = 0; i < 10; i ++){
        alert(i);
    }
*/
/*
    for(var i = 0; i < 10; i ++){}

    alert(i);   // 10
*/
/*
    // 可以使用逗号设置两个条件
    // 一旦其中一个完成了，就会停止
    for(var i = 0;i < 5,i < 3; i ++){
    }
    alert(i);   // 3
*/
/*
    // 死循环
    var i = 0;
    for(;true;){
        console.log(i);
        i++;
    }
*/
/*
    // 双循环  -> 通常用于 matrix/table
    for(var i = 0; i < 5; i ++){
        for(var j = 0; j < 5; j ++){
            console.log(i+','+j);
        }
    }
*/
</script>
```

#### for in 循环对象的
+ 可用下标 index
+ for(var i in 字符串/对象){}

Example:
```
<script>
    var arr = [1,2,3];
    for(var i in arr){
        console.log(i); // 0,1,2
    }

    var arr = [1,2,3];
    for(var i in arr){
        console.log(arr[i]); // 1,2,3
    }
    
    /*
    var string = 'abcde';
    for(var i in string){
        console.log(i); // 01,2,3,4
    }

    var string = 'abcde';
    for(var i in string){
        console.log(string.charAt(i));  // a,b,c,d,e
    }

    // 不兼容，有些浏览器，不支持
    var string = 'abcde';
    for(var i in string){
        console.log(string[i]); // a,b,c,d,e
    }
    */
</script>
```

#### for in 可用在 json 里
+ for(var i in 字符串/对象){}

Example:
```
<script>
    var json = {
        'name' : 'tgc',
        'age': '21',
        'height':'175'
    };
    for(var i in json){
        console.log(i);     // 'name','age','height'
    }

    for(var i in json){
        console.log(json[i]);   // 'tgc','21','175'
    }
</script>
```

#### while 循环
+ while(判断条件){执行的语句}
+ 里面循环结束了，外面就不循环了

Example:
```
<script>
/*
    var i = 0;
    while(i < 10){
        console.log(i++);   // 0 ~ 9
    }
*/
    // 里面的 while 循环一结束，外面的 while 循环就不动了
    var i = 0;
    var j = 0;
    while(i < 3){
        while(j < 3){
            console.log(i+','+j);
            j ++;
        }
        i ++;
    }

</script>
```

#### do-while 循环
+ 至少会执行一次循环

Example:
```
<script>
/*
    var i = 0;

    do{
        console.log(i++);   // 0 ~ 9
    }while(i < 10);
*/

    var i = 0;

    do{
        console.log(i++);   // 0
    }while(false);
    for(var i = 0; false ; i++){
        console.log(i);     // 没有执行
    }
</script>
```

#### for each 循环
+ 只能循环数组
+ 数组.forEach(function(e){alert(e);})

Example:
```
<script>

    var arr = [1,2,3];

    arr.forEach(function(a){
        console.log(a);
    })
</script>
```

#### 反循环

Example:
```
<script>

    for(var i = 10; i > 0; i --){
        console.log(i);     // 10 ~ 1
    }
</script>
```

#### 复杂化
Example:
```
<script>

    var f,l = 0;
    var arr = [1,2,3];

    [0,1,2,3].forEach(function(e){
        for(var i = 0; i < 5 ; i ++){
            for(var j = 0; j < 5 ; j ++){
                while( f < 3 ){ // 出问题
                    console.log('a');
                    do{
                        console.log(i+','+e+','+f+','+l+','+j);
                        l++;
                    }while(l<3);
                    f++;
                }
            }
        }
    })
    // 无法打印出来


    var f,l = 0;
    //  问题的所在
    while(f < 3){
        do{
            console.log(1); // 无法打印
            l ++;
        }while(l < 3);
        f ++;
    }

    // 解决
    do{
        console.log(l); // 0,1,2
        while(f < 3){
            f ++;
        }
        l ++;
    }while(l < 3);
</script>
```

## JavaScript 的逗号
+ ```,```
+ 这个 JS 语句没有完成
## JavaScript 的分号
+ ```;```
+ 这个 JS 语句完成了
