# 你有這樣的經驗嗎？

<div ml-4 pt-4>

<v-click>

明明功能或需求做出來了，頁面也長得沒什麼問題，但...

## 主管：

</v-click>

<v-clicks >

「這樣的寫法不容易維護」

「這段程式碼的 state 太複雜可以簡化」

「這裡的 useEffect 沒有必要」

「或是可能有過多的 re-render」 ... 等等

</v-clicks>

<v-click>

**明明已經寫出功能了，卻好像還是不太了解 react**

</v-click>

</div>

<!--
在進入正題之前，先聊一下我辦這場工作坊的初衷，在我剛開始工作的時候，常常發生以下問題

[click]
主管要求的功能或需求做出來了、頁面也長得沒什麼問題，但主管或 code review 你的人卻還是可以揪出一些問題：

[click]
例如這樣的寫法不容易維護

[click]
這段程式碼的 state 太複雜可以簡化

[click]
這裡的 useEffect 沒有必要

[click]
或是可能有過多的 re-render 等等。

明明已經寫出功能了，卻好像還是不太了解 react 常常被揪出問題


這就是我們今天這堂課要解決的核心問題 — React 的真正門檻，不在語法，在於你是否熟悉他的機制與思維
-->

---

# 從寫得出功能，到寫得出好程式碼

成為合格的 Junior 最重要的是**能完成主管給的任務，把需求或功能做出來**

<v-clicks>

但如果你想往上成為 Middle、Senior Level 來拿到更好的薪水，<span v-mark="{ at: '2', color: '#fdd321', type: 'underline' }">就不能只停留在把需求做出來
</span>。

而是要考慮更多面向，像是最佳實踐、效能優化、可維護性，這些就是你遲早要面對的門檻。

對於前端工程師來說，**熟悉你最常使用的工具，也就是 React 是最重要的第一步**

## Code Review 時

</v-clicks>

<div class="flex gap-4 mt-4 *:basis-1/4">

<Card v-click>
為什麼我會這樣寫？
</Card>

<Card v-click>
好處在哪？
</Card>

<Card v-click>
怎麼優化程式碼？
</Card>

<Card v-click>
怎麼解決效能問題？
</Card>

</div>

<!--
成為合格的 Junior 最重要的是能完成主管給的任務，把需求或功能做出來

[click]
但如果你想往上成為 Middle Level 或是 Senior 來拿到更好的薪水，就不能只停留在把需求做出來。

[click]
而是要考慮更多面向，像是最佳實踐、效能優化、可維護性，這些就是你遲早要面對的門檻。

[click]
那對於前端工程師來說，熟悉你最常使用的工具也就是 React 是最重要的第一步，

[click]
只要你能在 code review 或開會時說出

[click]
為什麼我會這樣寫？

[click]
好處在哪？

[click]
怎麼優化程式碼？

[click]
怎麼解決效能問題？等等

那你就不只是寫程式的人，而是會分析、會解決問題的人。

這樣的人，更有資格談晉升、談薪資，也更有價值。
-->

---

# 工作坊結束後，會帶你學到什麼？

<v-clicks>

<span v-mark="{ at: '1', color: '#fdd321', type: 'underline' }">
  不只是語法
</span>

幫助你建立一套理解 React、駕馭 React 的思維模型。

## 從根本開始

- React 是怎麼運作的？
- 為什麼 React 需要 state？re-render 又是什麼意思？
- 如何正確使用 state 與 effect？
- 哪些情況會造成 re-render？又有哪些地方其實是不必要的 re-render？
- 我們該怎麼觀察、分析，甚至優化這些 re-render？

所以這次工作坊的價值不在於「學會某幾個 Hook」，而是讓你能：
<br/>
看懂問題、分析原因、提出解法，**從寫功能的人，變成解決問題的人。**
</v-clicks>

<!--
所以我希望今天的工作坊結束後，

[click]
你不只是學到 React 的語法，或網路上能查到的資料

[click]
我的目標是幫助你建立一套理解 React、駕馭 React 的思維模型。

[click]
會從最根本的觀念開始理解：

[click]
包括

React 是怎麼運作的？

為什麼 React 需要 state？re-render 又是什麼意思？

哪些情況會造成 re-render？又有哪些地方其實是不必要的 re-render？

以及我們該怎麼觀察、分析，甚至優化這些 re-render？


[click]
所以這次工作坊的價值不在於「學會某幾個 Hook」，而是讓你能：

看懂問題、分析原因、提出解法，從寫功能的人，變成解決問題的人。
-->

---

<div class="h-full flex flex-col">
  <h1>
    工作坊流程大綱
  </h1>

  <div class="flex gap-8 my-auto font-bold">
    <Card class="basis-1/2 border-b-4 border-r-4 border-[var(--primary-highlight)]" v-click>
      <template #header >
        一、React 的心智模型
      </template>
        <ol class="text-sm mx-auto w-fit">
          <li>React 的核心運作觀念</li>
          <li>為什麼 React 需要 Re-render？</li>
          <li>Re-render 的本質是什麼？</li>
        </ol>
    </Card>
    <Card class="basis-1/2 border-b-4 border-r-4 border-[var(--primary-highlight)]" v-click>
      <template #header>
        二、State & Effect 用途與陷阱
      </template>
        <ol class="text-sm mx-auto w-fit">
          <li>useState 常見錯誤解析</li>
          <li>如何正確管理 state？</li>
          <li>useEffect 的真正意義與陷阱</li>
          <li class="text-[var(--secondary)]">中場休息</li>
        </ol>
    </Card>
  </div>

</div>

<!--
今天工作坊的流程分成 6 個主題

前兩個部分會先從 React 的核心觀念以及運作開始，
分別是 (照著大綱念
-->

---

<div class="h-full flex flex-col">
  <h1>
    工作坊流程大綱
  </h1>

  <div class="flex gap-8 my-auto font-bold">
    <Card class="basis-1/2" v-click>
      <template #header>
         三、4 種觸發 Re-Render 的場景
      </template>
        <ol class="text-sm mx-auto w-fit">
          <li>Re-render 為什麼會造成效能問題？</li>
          <li>4 種觸發 Re-render 的場景</li>
        </ol>
    </Card>
    <Card class="basis-1/2" v-click>
      <template #header>
        四、React 效能觀察與診斷
      </template>
        <ol class="text-sm mx-auto w-fit">
          <li>console.log 的正確使用</li>
          <li>React DevTools 的正確使用</li>
          <li>React Scan 效能觀察工具</li>
          <li class="text-[var(--secondary)]">中場休息</li>
        </ol>
    </Card>

  </div>

</div>

---

<div class="h-full flex flex-col">
  <h1>
    工作坊流程大綱
  </h1>

  <div class="flex gap-8 my-auto font-bold">
    <Card class="basis-1/2" v-click>
      <template #header>
        五、5 種記憶化策略與技巧
      </template>
        <ol class="text-sm mx-auto w-fit">
          <li>狀態下移與拆分</li>
          <li>內容上移的技巧與應用場景</li>
          <li>useMemo / useCallback 正確使用與誤區</li>
          <li>React.memo 的常見錯誤與策略</li>
          <li>useContext 的最佳使用方式與技巧</li>
        </ol>
    </Card>
    <Card class="basis-1/2" v-click>
      <template #header>
        六、React 的底層設計
      </template>
        <ol class="text-sm mx-auto w-fit">
          <li>Reconciliation & Diffing</li>
          <li>Key 值的真正意義</li>
          <li>在組件裡宣告其他組件的問題</li>
          <li class="text-[var(--secondary)]">QA 時間</li>
        </ol>
    </Card>
  </div>
  
</div>

<!--
如果沒問題，我們就正式開始今天的第一章節：

React 的核心運作觀念
-->
