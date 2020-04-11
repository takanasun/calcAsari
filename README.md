# calcAsari

## 解説だよ
### HEAD部分
```
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">
```
bootstrapっていう有名なCSSのフレームワークを直接読みだしてるよ。  
[bootstrap](https://getbootstrap.com/docs/4.4/getting-started/introduction/)

#### たとえば
```
<div class="row justify-content-md">
```
基本的に、Classの中身はBootstrapを使うときに使うお約束だとおもってもらっていい

### まずは数字
#### Event発火部分
```
<button class="btn btn-outline-primary btn-lg" type="button" onclick="inputValue(1)">1</button>
```
inputValueってやつに対して１っていう引数わたすぜ
#### Javascript
```
const inputValue = data => {
      if (currentValue.length <= 8) { 
        currentValue += data;
        result.value = currentValue;
      }
    };
```
inputValueって名前だぜ。もし入力済みの桁が８桁以下だった場合、  
currentValueってやつに引数をくっつけた物を渡す。（currentValueさんは文字列）  
resultっていうやつが18行目にいるよ

### 演算子
#### Event発火部分
```
<button class="btn btn-outline-primary btn-lg" type="button" onclick="calclationSign('+')">+</button>
```
＋ボタンを押したらcalclationSignってやつに＋押されたことを通知するぜ
#### Javascript
```
    const calclationSign = data => {
      if(tempValue == 0){
        tempValue = result.value;
      }else if (mark == "+" || mark == "-"){
        tempValue = eval(tempValue + mark + result.value);
      }
      mark = data;

      if(data == "+" || data == "-"){
        result.value = "";
      } else if(data == "="){
        mark = "";
        result.value = tempValue;
      }
      currentValue ="";
    }
```
引数でもらった演算子をdataに入れてるよ。
tempValueってやつが共通の変数としてあるよ。  
そいつは今まで計算された値がはいってるよ。
evalってやつをつかって、文字列になった計算式を数字としてtempValueにいれるよ

そのあとは今回入力された演算子をmarkっていうやつにいれこんでね。


