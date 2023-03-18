
<div align="center">
  <img height="60" src="https://icons8.com/icon/123603/react-native">
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

- A: 
- B: 
- C: 
- D: 

<details><summary><b>Ответ</b></summary>
<p>

#### Ответ: D
Описание

</p>
</details>

---

