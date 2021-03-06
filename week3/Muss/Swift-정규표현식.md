# Swift - 정규 표현식

Tags: 추가 내용+
주차: 3️⃣

## Regular Expression(정규 표현식)

- 특정한 규칙을 가진 문자열의 집합을 표현
- 주로 문자열 검색이나 email, ph, pw의 정규성 검사에 사용

정규식 예시)

![](https://images.velog.io/images/enchantee/post/9c9e94fb-e49f-42df-b0b7-f6e531825c6e/img-4.png)

대표적인 표현식

[[iOS - swift] 정규식 (Regex)](https://ios-development.tistory.com/277)

### 이메일 정규식 표현

```swift
let regex = "[A-Z0-9a-z._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,64}"
```

- @앞에는 대문자, 숫자, 소문자, 특수문자(._%+-)가 포함 가능
- **\\.** 콤마를 표현하기 위해서 **\\**사용
- @뒤로는 대문자, 소문자, 숫자 그리고 . 기준으로 맨 마지막 문자가 2~64길이

### 핸드폰 번호 정규식 표현

```swift
let regex = "^01[0-1, 7][0-9]{7,8}$"
```

- **^** 는 시작 앵커, **$** 는 끝 앵커
- 핸드폰 번호는 01로 시작
- 01다음에는 0,1,7 가능
- 그다음에 오는 숫자는 0~9 가능하고 7자리에서 8자리만 가능

### 패스워드 정규식 표현

```swift
let regex = "^(?=.*[A-Za-z])(?=.*[0-9])(?=.*[!@#$%^&*()_+=-]).{8,50}"// 8자리 ~ 50자리 영어+숫자+특수문자
```

- **^** 첫 앵커, **$** 끝 앵커
- **(?=.*** 로 시작: 조건문
- (?=.*...)(?=.*...)이와 같이 묶인것은 And조건이 아닌 Or조건
- **(?=.*[A-Za-z])** 대문자나 소문자 가능
- **(?=.*[0-9])** 숫자 가능
