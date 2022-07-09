# input

## 속성

### value

input의 value값을 조회할 수 있는 속성이다.

### autocomplete

```html
<input type="text" autocomplete />
```

인풋의 자동완성기능의 사용여부를 결정하는 태그이다.

- on => 자동완성 사용

- off => 자동완성 사용 x

자동완성으로 나타나는 여러 텍스트들은 사용자의 이전 기록을 추측하여 나타내준다.  
default값은 on이다.

사용하는 상황에 따라 autocomplete의 value를 유동적으로 사용할 수 있다.  
예를 들어, 아이디를 입력하는 input의 경우에는 `<input type="text" autocomplete="username"/>`라고 사용하고  
비밀번호를 입력하는 input의 경우에는 `<input type="text" autocomplete="new-password"/>`  
이메일을 입력하는 input의 경우에는 `<input type="text" autocomplete="email"/>`  
이라고 value값을 할당할 수 있다.

value값에 따라 브라우저가 그에 맞는 기록을 적절히 추측하여 나타내주기때문에 사용하는 목적 여부에 따라 적절한 autocomplete value값을 할당해주면 되겠다.

### required

```html

<form>
<input type='text' required/>
</form
```

required 속성은 form내에서 작용하는데 제출하기전에 required 속성이 부여된 input에 text가 없다면 form이 제출되지않는다.  
required 속성은 form내에서 필수기재사항을 입력받을 때 사용할 유용한 속성이다.

주의, form과 같이 사용할 때 효과가 있다.

### minlength & maxlength

```html
<form>
  <input type="text" minlength="4" maxlength="8" />
</form>
```

minlength와 maxlength는 form을 제출하기전 input에 입력할 텍스트를 제한할 수 있는 속성이다.  
위처럼 속성을 정해놓는다면 최소 4글자이상 8글자이하만 입력할 수 있다.

주의, form과 같이 사용할 때 효과가 있다.

### name

input의 name 속성은 input의 이름을 나타내는데 사용되고 name의 value값은 http request에 같이 보내진다.

```html
<form>
  <input type="text" minlength="4" maxlength="8" name="nickname" />
</form>
```

name value값은 form이 제출될 때 http request와 함께 서버로 보내진다.  
input의 name에 대한 정보를 서버로 보내 활용하고 싶다면 사용하면 된다.

(단, 자바스크립트에서 event.preventDefault를 하면 보내지지않는다.)

### disabled

```html
<input type="text" disabled />
```

input의 활성화 여부를 결정해 줄 수 있는 속성이다.

속성의 value값은 boolean 타입이고 default값은 false로 되어있다.

disabled = true라면 해당 input은 이용할 수 없게 된다.

주로 form내에서 필수로 기재해야하는 input이 기재 여부에 따라 제출 버튼의 활성화 여부를 결정하는데 사용된다.

## 유형

### input color

```html
<input type="color" />
```

색깔을 고를 수 있게 해주는 input 유형이다.

사용자가 원하는 색을 입력받아 여러 UI의 색깔을 변경한다든지 등에 사용할 수 있겠다.

### input number

```html
<input type="number" step="10" min="10" max="100" />
```

숫자를 입력받을 수 있는 input 유형이다.

value type은 number이고 onchange 이벤트를 적용할 수 있다.

min과 max 속성은 사용자가 입력할 수 있는 최소 숫자와 최대 숫자를 설정할 수 있는 값이다.

step 속성은 사용자가 클릭하거나 키보드 업다운을 통해 숫자를 증감하려할 때의 숫자 증감량이다.

### input range

```html
<input type="range" />
```

사용자가 숫자값을 조정할 때 사용하는 input 유형이다.

정밀한 값을 입력할 때 사용하기보단 주로 볼륨값을 조정할 때 사용된다.

### input password

```html
<input type="password" />
```

보안이 중요한 비밀번호를 입력받을 때 사용되는 유형이다.

텍스트를 입력받으면 사용자는 입력한 비밀번호를 볼 수 없고 일정한 동그라미 텍스트가 나열되는 것을 볼 수 있다.

## label(label의 for과 input의 id => match)

**label과 input을 같이 사용하면 얻게 되는 장점**

label은 input의 표제를 나타낼 때 사용해주며 사용자가 input의 용도를 명확히 알 수 있게 해준다.

input과 label을 같이 써주면 좋은 점은 input을 명시적으로 표현해줄 수 있다는 점과 label을 클릭해도 input에 포커싱이 되게 할 수 있다.

**label과 input을 연관시키는 방법**

1. label의 for와 input의 id match

```html
<label for="nickname">별명</label> <input type="text" id="nickname" />
```

label과 input을 연결시키기위해서는 label의 for값과 input의 id값을 동일하게 부여해주면된다.

다른 방법으로는 다음과 같이 input을 라벨로 묶어주면 된다.

2. label에 input nest

```html
<label> 별명<input type="text" /> </label>
```

## Reference

- https://developer.mozilla.org/ko/docs/Web/HTML/Element/Input
