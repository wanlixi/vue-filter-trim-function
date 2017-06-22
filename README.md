# -
输入框过滤空格、回车，自己用ES6语法封装的方法，可以通过 ``` import { checkInputValue } from 'api' ``` 引入到项目指定的文件中，即可使用，用法如下：
```
if (checkInputValue(inputValue) == '') {
//输入为空，请重新输入
}

```

```
export const checkInputValue = (inputValue) => {
    // 转义'<'和'>'，过滤用户输入的'<'和'>'（可以有效防止XSS攻击）
    inputValue && inputValue = inputValue.replace(/</g,'&lt;').replace(/>/g,'&gt;')
    inputValue = inputValue.replace(/\n/g,''));
    let result = JavaTrim(inputValue)
    function JavaTrim(str) {
      for (var i = 0; (str.charAt(i) == ' ') && i < str.length; i++);
       if (i == str.length) return '';
       var newstr = str.substr(i);
       for (var i = newstr.length-1; newstr.charAt(i) == ' ' && i >= 0; i--);
            newstr = newstr.substr(0, i + 1);
            return newstr;
    }
    return result;
}


```
