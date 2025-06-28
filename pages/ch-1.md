---
layout: center
transition: slide-left
---

# React 的心智模型

---
layout: center
---

<CenterTitle number="1" subtitle="React 核心觀念">
  <span class="font-mono">UI = f(state)</span>
</CenterTitle>

<!--
相信你們在學 React 的過程中，可能會聽過這句話

React 是聲明式（declarative）框架

聲明式是什麼意思？
-->

---

# 聲明式是什麼意思？

<v-clicks>

只要描述 <span v-mark="{ color: 'var(--secondary)', at: 1 }">「你想要的結果是什麼」，不用去寫「怎麼一步步達成這個結果」</span>

<h2>

描述你想要的 UI 是什麼樣子（利用 state、jsx 等）
<br/>
<br/>
React 會在背後處理所有事情

</h2>
</v-clicks>

<!--
他的意思是我們只要描述「你想要的結果是什麼」，不用去寫「怎麼一步步達成這個結果」。

而在 React 裡的意思就是
你只需要描述你想要的 UI 是什麼樣子（利用 state、jsx 等）， React 會在背後處理所有事情

我們來看個具體的例子
-->

---

# 聲明式的範例

假設我們現在想在點擊按鈕時，切換顯示一段文字（顯示/隱藏）。

````md magic-move
```js
// 原生 JavaScript 的寫法 - 命令式
<button id="toggleBtn">切換</button>
<div id="text" style="display: none;">Hello World</div>

<script>
  const btn = document.getElementById('toggleBtn');
  const text = document.getElementById('text');

  btn.addEventListener('click', () => {
    if (text.style.display === 'none') {
      text.style.display = 'block';
    } else {
      text.style.display = 'none';
    }
  });
</script>
```

```js
// React 的寫法 - 聲明式
function App() {
  const [visible, setVisible] = useState(false);

  return (
    <div>
      <button onClick={() => setVisible(!visible)}>切換</button>
      {visible && <div>Hello World</div>}
    </div>
  );
}
```
````

<!--
假設我們現在想在點擊按鈕時，切換顯示一段文字（顯示/隱藏）。

在原生的 JS 中，我們需要一步一步告訴程式該怎麼做：

1. 先抓取 DOM。
2. 然後加監聽器。
3. 控制 display 的邏輯

這就是命令式 —— 我們要把「怎麼做」全寫出來了。如果你有寫過稍微大型的原生 JS 專案，你就可以很清楚感受到這是一件非常麻煩的事情，也不容易去維護，因為我們要寫出所有的邏輯。


而在 React 你只要描述「根據狀態，UI 要長什麼樣」：

1. 定義狀態 visible。
2. UI 是依據 visible 值來決定要不要顯示 <div>Hello World</div>。
3. 我們不用處理 DOM，也不用設定 display，不管元素要不要出現 —— React 會幫你根據 state 來做。

這就是 UI = f(state) 的意思。
-->

---
layout: center
---

# `UI = f(state)`

<v-clicks>

在 React 裡，UI 是由 state 推導出來的。

UI 就是執行一個 function 的結果

</v-clicks>

<!--
從上面的範例，我們可以感受到
在 React 裡，UI 是由 state 推導出來的。

也就是標題的公式

換句話說，UI 就是執行一個 function 的結果
而結果會因為 state 的改變而有所不同

很多 React 新手，因為沒有理解這個概念，所以會覺得 React 很難。

包括我一開始也是，但對 React 重要的是資料，以及資料該怎麼顯示

知道這一點後，整個開發後想法就會變得清晰。useState、useEffect 也不再是死背，而是為了處理資料變化的具體工具。
-->

---

# State 改變會發生什麼？

從剛剛看到的範例中，我們知道 UI 是根據 state 來決定的：

```js {3}
<div>
  <button onClick={() => setVisible(!visible)}>切換</button>
  {visible && <div>Hello World</div>}
</div>
```

<v-clicks>

那 state 改變時，會發生什麼事？

## React 會重新 render（Re-render）整個 component 來更新 UI

</v-clicks>

<!--
從剛剛看到的範例中，UI 是根據 state 來決定的：

{visible && <div>Hello World</div>} 

這代表什麼？只要 state 改變，UI 就應該跟著改變。

那問題來了：

React 是怎麼知道我們改了 state？又是怎麼讓 UI 更新的？

答案就是“React 會重新 render（Re-render）整個 component。

Re-render 也是今天工作坊的一大主題，我們會在後面更詳細的介紹。
-->

---
layout: center
---

<CenterTitle number="2" subtitle="React Re-render 的">
本質是什麼？
</CenterTitle>

<!--
延續前面的主題，我們知道當 state 改變時，React 會重新渲染（Re-render）整個 component，以產生對應的新 UI。
-->

---

# 那 Re-render 時，React 做了哪些事情呢？

- state 改變時，React 會重新「執行」整個 component function
- 用新的 state 產出新的 UI 結構（JSX → Virtual DOM）

透過 `console.log()` 來觀察 Re-render 順序:

```js
export default function App() {
  console.log('call function');

  const [count, setCount] = useState(0);

  return (
    <div>
      {console.log('return jsx')}
      <h1>現在的數字：{count}</h1>
      <Button onClick={() => setCount(count + 1)}>+1</Button>
    </div>
  );
}
```

<!--
其實 Re-render 非常單純，他會重新執行整個 component function，並用新的 state 來產出新的畫面結果

其實 Re-render 的動作很單純：它會重新執行整個 component function，並根據最新的 state 來產生新的畫面結構（Virtual DOM）。

我們可以透過 console.log() 來實際觀察到 re-render 時的順序
-->

---

<Video>
<source src="/ch-1/1-2/0.mp4" type="video/mp4" />
</Video>

每次 Re-render，React 都會重新執行這個 function component，從頭執行一次函式並回傳新的 JSX。

<!--
每次當我們按下按鈕、改變 state，就會在 console 中依序看到：

call function  
return jsx

這代表：每次 Re-render，React 都會重新執行這個 function component
從頭執行一次函式並回傳新的 JSX。
-->

---

# Re-render ≠ 直接更新畫面

<div>

<v-click>

Re-render 的過程是

</v-click>

<v-clicks>

1. 根據新的 state，重新產生新的 UI（Virtual DOM）
2. 把新的 Virtual DOM 和舊的版本進行比對，找出差異，只更新那些真的需要改變的部分
3. 這個過程就是 <span v-mark="{ color: 'var(--secondary)', at: 4 }">Reconciliation</span>

</v-clicks>

<v-click>

## 比較完後，React 才就會進入下一個階段：**Commit Phase**

</v-click>

</div>

<!--
但這邊有一個很重要的觀念要補充：

Re-render 並不等於「直接更新畫面」。

Re-render 的本質只是「根據新的 state，重新產生新的 UI 描述（Virtual DOM）」。

接著，React 會把這個新的 Virtual DOM 和舊的版本進行比對，找出差異，只更新那些真的需要改變的部分。

這個比對過程就是很有名的 Reconciliation，中文翻譯叫調和，我們會在後面的章節再深入討論，這裡先有個概念即可。

當 Re-render 完組件後，React 就會執行下個階段 Commit Phase
-->

---
layout: center
---

<CenterTitle number="3" subtitle="Re-render 之後">
Commit Phase (階段)
</CenterTitle>

<!--
當 React 完成 Re-render，產出新的 Virtual DOM 後，接下來就會進入 Commit Phase，這時 React 才會真正去「d更新畫面」和執行副作用。
-->

---

# Commit Phase 做了哪些事情？

<VCenter>

<HStack class="max-w-2xl mx-auto">

<v-clicks>

<Card headerNumber="1">
<template #header>
更新 DOM
</template>

1.  加入 / 移除 / 修改 DOM 元素
2.  設定 ref

</Card>

<Card headerNumber="2">
  <template #header>
  執行副作用
  </template>

1. useLayoutEffect（畫面改完馬上執行，同步）
2. useEffect（畫面畫完後才執行，非同步）

</Card>

</v-clicks>

</HStack>

</VCenter>

<!--
commit phase 的底層實現非常複雜，其實我們也沒必要真的去看懂 React 的原始程式碼

但我們最少要知道在 commit phase 做了這些事情

1. 更新真實 DOM
  加入 / 移除 / 修改 DOM 元素
  設定 ref

2. 執行副作用
   useLayoutEffect（畫面改完馬上執行，同步）
   useEffect（畫面畫完後才執行，非同步）
-->

---

# CH 1 總結

<v-click>

## 為什麼要理解 UI = f(state) 和 re-render？

</v-click>

<v-click>

這是後面所有效能優化的基礎，像是：

</v-click>

<v-clicks>

- 為什麼要記憶化？因為不想讓 UI 不必要地重算。
- 為什麼要觀察 re-render？因為要搞清楚是誰的 state 變了。
- 為什麼有些 useEffect 會跑太多次？因為依賴的 state 每次 render 都在變。

</v-clicks>

<v-click>

## React 的運作流程

</v-click>

<v-clicks>

- **Trigger**: State 改變
- **Re-render**: 算出需要更新的 DOM (Reconciliation)
- **Commit**: 真正更新 DOM、執行 Effect

</v-clicks>

<v-click>

## **Trigger <span font-mono>-></span> Re-render <span font-mono>-></span> Commit**

</v-click>

<!--
為什麼要理解 UI = f(state) 和 re-render 呢？

因為這是後面所有效能優化的基礎，像是：

為什麼要記憶化？因為不想讓 UI 不必要地重算。

為什麼要觀察 re-render？因為要搞清楚是誰的 state 變了。

為什麼有些 useEffect 會跑太多次？因為依賴的 state 每次 render 都在變。

這些都跟 state、re-render、commit 有關係。

React 的運作流程

最後總結一下 React 的運作流程，分別是

Trigger: State 改變

Re-render: 算出需要更新的 DOM (Reconciliation)

Commit: 真正更新 DOM、執行 Effect

有了大致的 React 運作流程後，我們就可以更仔細的聊聊 state 和 effect
-->
