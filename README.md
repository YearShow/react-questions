
<div align="center">
  <img height="60" src="https://cdn0.iconfinder.com/data/icons/logos-brands-in-colors/128/react_color-512.png">
  <h1>Вопросы по React</h1>
</div>
    
---

###### 1. Что выведется в консоли и чему будет равен clicks, если нажать на кнопку 10 раз за полторы секунды?

```javascript
export function Clicker() {
    const [clicks, setClicks] = useState<number>(0);

    let counter = 0

    const onClick = () => {
        setTimeout(() => {
            counter++
            console.log(counter)
            setClicks(clicks + 1);
        }, 1000);
    };

    return (
        <div>
            <hr/>
            {clicks}
            <button onClick={onClick}>
                Increment
            </button>
        </div>
    );
}
```

<details><summary><b>Ответ</b></summary>
<p>

#### Ответ
clicks передаётся в setClicks через замыкание, и, пока не исполнился setTimeout, он равен 0. Поэтому все клики, которые мы делаем в первую секунду, будут выполняться со значением '0 + 1', а клики которые будут делаться после того, как сработал первый setTimout, будут подставлять 1.
counter увеличивается с каждым кликом, которые происходит в первую секунду. Однако после того, как через 1 секунду срабатывает setClicks, меняется локальный стейт, компонент обновляется, и counter снова становится равным 0. Поэтому после срабатывания setTimeout counter снова будет инкрементиться с 0/

</p>
</details>

---

###### 2. Предложить варианты оптимизации кода

```javascript
const heavyFunc = (count)=>{
    return Math.floor(Math.random()*count)
};
const LazyInit = (props)=>{
    const [count, setCount] = useState(heavyFunc(props.count));
    return (
        <> 
            {count}
            <button onClick={()=>setCount((prevProps)=>++prevProps)}>
              Increment
            </button>
        </>
    )
}
```

<details><summary><b>Ответ</b></summary>
<p>

#### Ответ
Функция будет вызываться в useState при каждом изменении стейта, и чтобы она вызвалась только один раз, нужно передать коллбэк

</p>
</details>

---
