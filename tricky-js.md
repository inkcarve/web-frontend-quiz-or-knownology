# Trick Js
#### *Damn it ! Javascript !*

### 1
var text = 'out';  
function test() {  
&nbsp;&nbsp;&nbsp;&nbsp; console.log(a);  
&nbsp;&nbsp;&nbsp;&nbsp; var a = 'in';  
}  
test();

output:
```
undefined
```

### 2
console.log('1');  
(function(){  
&nbsp;&nbsp;&nbsp;&nbsp; console.log('2');  
})()  
console.log('3');  

output:
```
'1'
'2'
'3'
```

### 3
for(var i = 0; i < 5; i++) {  
&nbsp;&nbsp;&nbsp;&nbsp; setTimeout(function() {  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; console.log(i);
    }, 0);  
}  

output:
```
5
5
5
5
5
```

### 4
var a = 1, b= '1';  
console.log(a==b);  
console.log(a===b);  
console.log(a==b==true);  
console.log(a===b==true);  
console.log(a===b===true);  
console.log(a===b===false);  

output:
```
true
false
true
false
false
true
```

### 5 Write a function find string in array which contain longest repeat char.
```
function matchLongestRepeatString (arr){ 
    let result, maxNow=0;
    arr.forEach((s,i)=>{
		console.log(s)
        if(s.length < maxNow)return;
        let matchArray = [];
        matchArray = s.match(/(.)\1+/g);
		console.log(matchArray);
        if(!matchArray)return;
        matchArray.forEach((s2, j)=>{
            if(s2.length > maxNow){
                console.log(s);
                console.log(s2);
                result = s;
                maxNow = s2.length;
            }
        })
    })
    return result;
}

** check repear char /(.)\1+/g one times up
** check repeat chart /(.)\1\1+/g twice times up
... etc
```


### 5
console.log('1'+1);  
console.log('1'-1);  
console.log('1'*1);  
console.log(1*'1');  
console.log('A'+'B'+1);  
console.log('A'-'B'+1);  
console.log('A'-'B'-1);  
console.log('A'*'B'*1);  

output:
```
'1'
0
1
1
'AB1'
NaN
NaN
```

### 6
Write some IIFE
```
(function(){}){}
(function(){}())
tricky below:
!function(){}()
~function(){}()
+function(){}()
-function(){}()
!function(){}()
```

### 7 
setTimeout(()=>{  
&nbsp;&nbsp;&nbsp;&nbsp; console.log('1');  
},0);  
console.log('2')

output:
```
2
1
```