# Week 02_Auto Layout

# Auto Layout

<aside>
๐ **์ ์ฝ ์กฐ๊ฑด(Constraints)**์ ๋ฐ๋ผย  ๋ทฐ ๊ณ์ธต ๊ตฌ์กฐ์ ์๋ ๋ชจ๋  ๋ทฐ์ ํฌ๊ธฐ์ ์์น๋ฅผ **๋์ ์ผ๋ก ์ง์ **ํ๋ ๊ฒ

</aside>

### ์ ํ์ํ๊ฐ?

ํ๋ฉด์ ๊ตฌ์ฑ์์๋ค์ ์ขํ๋ก ์ ํด๋ฒ๋ฆฌ๋ฉด, ํด์๋๊ฐ ๋ค๋ฅธ ํ๋ฉด์์ ๋ค๋ฅด๊ฒ ํํ๋  ์ ์๋ค. ์๋ ์ฝ๋์์ ์์ ์์ x๋ก๋ 30๋งํผ y๋ก๋ 80๋งํผ ๋จ์ด์ง ๊ณณ์ ๋๋น 350, ๋์ด 200์ผ๋ก ์ฌ์ง ๋ฃ์์ง๋ง iPhone8๊ณผ iPad๋ ํด์๋๊ฐ ๋ค๋ฅด๊ธฐ ๋๋ฌธ์ ์ ๋ด์์ผ๋ก ๋ํ๋๊ฒ ๋๋ค. 

```swift
let myView: UIImageView = .init(frame:.init(x: 30, y: 80, width: 350, height: 200))
```

![Untitled](Week%2002_Au%2032194/Untitled.png)

๊ฐ๋ฅํ ๋ชจ๋  ๊ธฐ๊ธฐ์ ํด์๋๋ฅผ ๋ฐ์์ ๊ณ์ฐํด์ ๋ฃ์ ์์ผ ์์ง๋ง,,, ๋๋ฌด๋ ๋นํจ์จ์ ์ธ ๊ณผ์ ์ด๋ค. ๊ทธ๋์ ์ฐ๋ฆฌ์ ์ฐฉํ๊ณ  ๋๋ํ Auto Layout์ โ์ ๋ค๋ผ๋ฆฌ ์๋์ ์ธ ์์น๋ง ์๋ ค์ค ๋ด ๋ด๊ฐ ์์์ ๊ตฌ์ฑํด์คใใโํ๊ณ  ํด์ค๋ค.

### Constraints ์ ์ฝ ์กฐ๊ฑด

ํ๋ฉด์ ๊ตฌ์ฑ์์๋ค ๊ฐ์ ์๋์ ์ธ ์์น๋ ํฌ๊ธฐ๋ฅผ ์ง์ ํด์ฃผ๋ ๊ฒ์ด Constraints์ด๋ค. ์๋ ๊ทธ๋ฆผ์ฒ๋ผ ์ข์ฐ๋ก 30, ์๋ก 50๋งํผ ๋จ์ด์ง ๊ณณ์ ๋์ด๊ฐ 200์ธ imageView๋ฅผ ๋์๋ผ! ํ๋ ๊ฒ์ด๋ค.

![Untitled](Week%2002_Au%2032194/Untitled%201.png)

์ ์ฝ์กฐ๊ฑด์ ์ค ๋, ๋ฐ๋์ ํฌ๊ธฐ์ ์์น๋ฅผ ์๊ฒ๋ ์ค์ผํ๋ค. ๋ช์๋ฅผ ํด์ฃผ๋ , ๋ค๋ฅธ Constraints๋ก ์ถ๋ก ์ ํ  ์ ์๋ ์ง ๊ฐ์ ๋ง์ด๋ค. ์ ์๋ก ๋ณด๋ฉด width๋ ์ง์  ์ฃผ์ง ์์์ง๋ง ์ผ์ชฝ ์ค๋ฅธ์ชฝ ๊ณต๋ฐฑ์ ํฌ๊ธฐ๋ฅผ ํตํด width๋ฅผ ์ถ๋ก ํด ๋ผ ์ ์๋ค. ๋, ์๋ ๊ณต๋ฐฑ์ ์ค์ ํ์ง ์์๊ธฐ ๋๋ฌธ์ height๋ฅผ ๋ช์ํด์ฃผ์๋ค. ๊ทผ๋ฐ ์ฌ๊ธฐ์ width๋ Constraints์ ์ถ๊ฐํ๋ฉด, width์ ๋ํ ์ ๋ณด๊ฐ ๋๊ฐ์ง๊ฐ ์๊ธฐ๊ธฐ ๋๋ฌธ์ ์๋ฌ๊ฐ ๋ฌ๋ค...

### Constraints ์ ์์

1. ํฌ๊ธฐ์ ๋ํ ์์ : height, width
2. ์์น์ ๋ํ ์์
    1. margin : top, bottom, leading(left), tailing(right) ๊ฐ๊ฐ ์, ์๋, ์ผ์ชฝ, ์ค๋ฅธ์ชฝ์ผ๋ก๋ถํฐ ์ผ๋ง๋ ๋จ์ด์ ธ์์์ง
    2. alignment : ์ ๋ ฌ๊ธฐ์ค. x,y์ถ์ผ๋ก๋ถํฐ ์ผ๋ง๋ ๋จ์ด์ ธ ์์๊ฑด์ง, ๋ค๋ฅธ ์์๋ค๊ณผ ์ ๋ ฌํ ๊ฑด์ง
    

### ํฌ๊ธฐ ๊ฒฐ์ ํ๋ ๋ฒ

1. height, width Constraints ์ฃผ๊ธฐ
2. margin ์ ๋ํ ์ ์ฝ์กฐ๊ฑด์ผ๋ก ์ถ๋ก ํ  ์ ์๊ฒ ํ๊ธฐ
3. ๊ธฐ์ค ์์์ ๋ํ ๋น์จ
    
    ![Untitled](Week%2002_Au%2032194/Untitled%202.png)
    
4. Intrinsic Content Size : ๋ทฐ๊ฐ ์๋ ๊ฐ์ง๊ณ  ์์๋ ํฌ๊ธฐ๋ฅผ ๊ณ ์  ์ฝํ์ธ  ํฌ๊ธฐ(Intrinsic Content Size)๋ผ๊ณ  ํ๋ค. ์ฆ ์คํ ๋ ์ด์์์ ์ํด ๋ณ๊ฒฝ๋๊ธฐ ์  ์๋ณธ ํฌ๊ธฐ๋ฅผ ์๋ฏธํ๋ค.

![Untitled](Week%2002_Au%2032194/Untitled%203.png)

### **์ ์ฝ ์ฐ์ ๋(Constant Priority)**

์คํ ๋ ์ด์์์์ ์ ์ฝ์ด ๊ฐ์ง๋ ์ฐ์ ๋๋ฅผ ๋งํ๋ค. ๋ง์ฝ ์ ์ฝ์ด ์ถฉ๋ํ๋ ๊ฒฝ์ฐ, ์ฐ์ ๋๊ฐ ๋์ ์ ์ฝ๋ถํฐ ๋ ์ด์์์ ์ ์ฉ๋๋ค. ๊ณ ์  ์ฝํ์ธ  ํฌ๊ธฐ๋ณด๋ค ๋ทฐ๊ฐ ์ปค์ง์ง ์๋๋ก ์ ํํ๋ย **์ฝํ์ธ  ํ๊น ์ฐ์ ๋(Contents Hugging Priority)**ย ์, ์ด์ ๋ฐ๋๋ก ์์์ง์ง ์๋๋ก ์ ํํ๋ย **์ฝํ์ธ  ์ถ์ ๋ฐฉ์ง ์ฐ์ ๋(Contents Compression Resistance Priority)ใ**ย ๊ฐ ์๋ค.

## Safe Area

<aside>
๐ **์์คํ์ ์ํด ๊ฐ๋ ค์ง ์ ์๋ ๋ถ๋ถ**์ ๋ง์ง์ ์์ฒด์ ์ผ๋ก ๊ฐ๊ณ  ์๋ ์์ญ

</aside>

์ฑ์ ํ๋ฉด ์ ์ฒด๋ก ์ฌ์ฉํ๋ค๋ฉด ๊ฐ๋ ค์ง๋ ๋ถ๋ถ์ด ์๊ธด๋ค. ๋จธ๋จธ๋ฆฌ ๋ถ๋ถ์ด๋, ์๋จ๋ฐ, ๋ชจ์๋ฆฌ ๋ถ๋ถ ๋ฑ.. ๊ทธ๋์ Safe Area๋ ๊ทธ๋ฌํ ๋ถ๋ถ์ ์ ์ธํ ์์ญ ์์์ ๊ฐ๋ฐํ  ์ ์๊ฒ ํด์ค๋ค. ์๋ ๊ทธ๋ฆผ์ ์ผ์ชฝ์ด ์ ์ฒดํ๋ฉด์ธ Super View ์์ญ, ์ค๋ฅธ์ชฝ์ Safe Area์ ์์ญ์ ๋ณด์ฌ์ฃผ๊ณ  ์๋ค. 

![Untitled](Week%2002_Au%2032194/Untitled%204.png)

![Untitled](Week%2002_Au%2032194/Untitled%205.png)