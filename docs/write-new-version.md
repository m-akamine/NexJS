# 
## スマートな書き方

### 関数部分

教科書の書き方
``` function
exprot default function Home(){
    return(
        <div>
            <h1>CUBE</h1>
            <p>アウトプットしていくサイト</p>
        </div>
    )
}

```
↓
``` function
const Home = () => {
    return(
        <div>
            <h1>CUBE</h1>
            <p>アウトプットしていくサイト</p>
        </div>        
    )
}
```


## Next.jsの書籍とのバージョン違う部分での書き方