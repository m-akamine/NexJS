# 正実メモ
## スマートな書き方

### 関数部分 P33

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

授業での書き方
``` function
const Home = () => {
    return(
        <div>
            <h1>CUBE</h1>
            <p>アウトプットしていくサイト</p>
        </div>        
    )
}
export default Home

```

### propsの書き方

教科書の書き方
```
function EachPost({title, url}){
    return(
        <article>
            <a href={url}>
                <h3>{title}</h3>
            </a>
        </article>
    )
}
```


## Next.jsの書籍とのバージョン違う部分での書き方


## neovim作業でのテクニック
### vim 複数ファイル 切り替え
次へ → `:next`  
前へ → `:prev`  

### neovim での emmet 展開
`ctrl+y` のすぐ後に` , `   