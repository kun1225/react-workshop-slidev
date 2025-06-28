---
layout: cover
transition: slide-left
---

<p class="text-xl !mb-12 text-[var(--mute)]">ThisWeb 請網這邊走</p>

# React 效能優化實戰工作坊

## 3 小時掌握 React 進階技術 x 底層思維

---

# 你有這樣的經驗嗎？

<div ml-4 pt-4>

<v-clicks >

明明功能或需求做出來了，頁面也長得沒什麼問題，但...

<h2>
  主管：
</h2>
<p>
  「這樣的寫法不容易維護」
</p>
<p>
  「這段程式碼的 state 太複雜可以簡化」
</p>
<p>
  「這裡的 useEffect 沒有必要」
</p>
<p>
  「或是可能有過多的 re-render」
</p>
<p>
  ...
</p>

</v-clicks>

</div>

<!--
主管要求的功能或需求做出來了、頁面也長得沒什麼問題，但主管或 code review 你的人卻還是可以揪出一些問題：例如這樣的寫法不容易維護、這段程式碼的 state 太複雜可以簡化、這裡的 useEffect 沒有必要，或是可能有過多的 re-render 等等。

這時候你可能會覺得自己已經寫出功能了，為什麼好像還是不太了解 react 長常常被揪出問題

這就是我們今天這堂課要解決的核心問題 — React 的真正門檻，不在語法，在於你是否熟悉其機制與思維
-->

---

# 從寫得出功能，到寫得出好程式碼

<v-clicks>

成為合格的 Junior 最重要的是**能完成主管給的任務，把需求或功能做出來**

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
成為合格的 Junior 最重要的是能完成主管給的任務，把需求或功能做出來，但如果你想往上成為 Middle Level 或是 Senior 來拿到更好的薪水，就不能只停留在把需求做出來。

而是要考慮更多面向，像是最佳實踐、效能優化、可維護性，這些就是你遲早要面對的門檻。

你會發現，大多數 Junior 工程師卡關，不是因為「不會做功能」，而是做出來的功能效能差、維護性低。

那對於前端工程師來說，熟悉你最常使用的工具也就是 React 是最重要的第一步，

只要你能在 code review 或開會時說出，為什麼我會這樣寫？好處在哪？怎麼優化程式碼？怎麼解決效能問題？等等

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
- 哪些情況會造成 re-render？又有哪些地方其實是不必要的 re-render？
- 我們該怎麼觀察、分析，甚至優化這些 re-render？

所以這堂課的價值不在於「學會某幾個 Hook」，而是讓你能：

看懂問題、分析原因、提出解法，**從寫功能的人，變成解決問題的人。**
</v-clicks>

<!--
這也是我舉辦這次工作坊的目的，

我希望今天的工作坊結束後，你不只是學到 React 的語法，或網路上能查到的資料

我的目標是幫助你建立一套理解 React、駕馭 React 的思維模型。

會從最根本的觀念開始理解：

React 是怎麼運作的？

為什麼 React 需要 state？re-render 又是什麼意思？

哪些情況會造成 re-render？又有哪些地方其實是不必要的 re-render？

以及我們該怎麼觀察、分析，甚至優化這些 re-render？

所以這堂課的價值不在於「學會某幾個 Hook」，而是讓你能：

看懂問題、分析原因、提出解法，從寫功能的人，變成解決問題的人。

如果你準備好，我們就正式開始今天的第一章節：

React 的核心觀念：「UI = f(state)」
-->

---

<div class="h-full flex flex-col">
  <h1>
    工作坊流程大綱
  </h1>

  <div class="flex gap-8 my-auto font-bold">
    <Card class="basis-1/3">
      <template #header>
        React 的心智模型
      </template>
      <template #content>
        <ol>
          <li>React 的核心運作觀念</li>
          <li>為什麼 React 需要 Re-render？</li>
          <li>Re-render 的本質是什麼？</li>
        </ol>
      </template>
    </Card>
    <Card class="basis-1/3">
      <template #header>
        State & Effect 用途與陷阱
      </template>
      <template #content>
        <ol>
          <li>useState 常見錯誤解析</li>
          <li>如何正確管理 state？</li>
          <li>2-3 useEffect 的真正意義與陷阱</li>
        </ol>
      </template>
    </Card>
    <Card class="basis-1/3">
      <template #header>
        4 種觸發 Re-Render 的場景
      </template>
      <template #content>
        <ol>
          <li>Re-render 為什麼會造成效能問題？</li>
          <li>4 種觸發 Re-render 的場景</li>
        </ol>
      </template>
    </Card>

  </div>

</div>
