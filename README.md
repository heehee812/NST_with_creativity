
## HOW TO USE NST TO IMPLEMENT THREE ARTISTIC CREATIVITIES

### Introduction
此篇將要介紹利用 NST（Neural Style Tranfer）實作三種想像力的方法（Combinational, Exploratory, Transformational）。想像力，包含兩種元素，第一個是 novel，第二個是 (Creativity can be defined as the ability to generate novel, and valuable, ideas.)，而該如何利用 NST ，意即，再創造點子時使用風格轉移得技術，是我們這篇 study 要討論的方向。Combinational Creativity，顧名思義為將兩個原有的點子結合，變成一個複合式的點子，而在新的點子中可以看到兩的點子的特點。Exploratory Creativity，為將舊有的點子、概念加以改造變成新的點子，好比食譜，利用提供好的原料做出一道料理。這個點子除了可以看到既有點子的影子外，也帶出了新的概念。Transformational Creativity，與 Exploratory Creatvity 類似，都透過了既有的點子帶出了新的概念，但除此之外，Transformational Creativity 是將就有的點子完全改造及轉換成新的樣子。

### Method
#### Combinational Creativity
當一個創作概念保有大多原創做的特性時，意即創作者將原有概念結合成一個新的創作，我們將其稱作 Combinational Creativity。而依照保原創作 Content 及 Style 的設計特性，我們可想出四種可能的實現方法。第一種，保有原有的 Style 結合部分 Content。第二種，保有部分 Style 結合步部分 Content。第三種，保有部分 Style 結合所有 Content。第四種，保有原有 Style 結合所有 Content。而本 Study 中，我們將 Content 取 Grayscale ，其中白色部分作為被保留的面積（Figure 1-1），如此一來，不同的圖片都會有不同被保留的元素，而將黑色部分則轉換為Style （Figure1-2），最後取得結果。

> Figure 1-1. 選擇 content 中要保留的元素
<img width="596" alt="Screenshot 2024-04-04 at 7 40 02 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/47854fd9-acdb-4db1-879d-911b3ce5560a">


> Figure 1-2. 從 Style 中取出 Content 黑色部分的遮罩
<img width="597" alt="Screenshot 2024-04-04 at 7 41 02 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/56fd8e65-006c-4b17-9bd2-71c66ac39ec9">


#### Exploratory Creativity
當一個作品出現原有作品轉換過的元素及類似模式時，我們稱作為 Exploratory Creativity。而依照改造原有作品特性的特點，透過元素的排列方式及大小變化，並結合 Style 可實現。故我們利用對 Content 取Grayscale 選出可被重新排列的元素，並改變其大小（Figure2-1），而將剩下的部分利用 NST 技術將其與 Style做結合（Figure2-2）。

> Figure 2-1. 重新排列及改變 content 中元素大小
<img width="594" alt="Screenshot 2024-04-04 at 7 41 34 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/54e0dd93-98c1-4953-b877-fd0cb1688fcc">

> Figure 2-2. 將重新排列過後的 content 與 style 做結合
<img width="591" alt="Screenshot 2024-04-04 at 7 42 44 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/d73454ff-fd42-4a80-a469-cc7ce9750838">

#### Transformational Creativity
當一個作品幾乎不同於原創作，僅可從一些 pattern 中找到相似之處，我們推測這是 Tranformational Creativity。而依照圖片特性被改變的特徵來看，我們須盡可能的改變圖片參數，因此，我們先透過 Grayscale 技術取出 Content 中白色部分作為改變顏色參數的範圍，並改變元素大小，並保留剩下部分（Figure3-1）。之後再透過 NST 技術中，計算 Content 及 Style Loss function 的方式，並利用 Gradient descent 找出 Content 與 Style 中最相容的 pattern 作為output（Figure3-2）。

> Figure 3-1. 改變 content 中元素大小及顏色
<img width="593" alt="Screenshot 2024-04-04 at 7 45 55 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/1fbc5619-ee06-4d32-9b8e-bad164ecb537">

> Figure 3-2. 利用 NST 轉換 content 及 style
<img width="596" alt="Screenshot 2024-04-04 at 7 46 07 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/7c3667b2-15f1-48dd-b3bd-545b73a358fb">

### Result
這邊放幾個例子來看看實際執行結果。

**Example 1**
<img width="554" alt="Screenshot 2024-04-04 at 7 47 19 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/1254235f-8c93-4ad3-b7e1-581997d52ef1">
<img width="381" alt="Screenshot 2024-04-04 at 7 47 10 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/6dbd4400-c8f3-4238-b595-803ede981898">

**Example 2**
<img width="590" alt="Screenshot 2024-04-04 at 7 47 38 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/bd695eb1-aba0-4c58-ada6-1700d8f3f388">
<img width="460" alt="Screenshot 2024-04-04 at 7 47 29 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/eff4893b-fabe-4a6f-8762-a8cea95db811">

**Example 3**
<img width="598" alt="Screenshot 2024-04-04 at 7 47 55 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/d0ef0f3d-f1ca-4634-a2f3-a778b9dfa94b">
<img width="569" alt="Screenshot 2024-04-04 at 7 47 45 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/ecd4a5db-e041-458f-9114-40c7c0aaacf9">


**Example 4**
<img width="598" alt="Screenshot 2024-04-04 at 7 48 03 PM-min" src="https://github.com/heehee812/NST_with_creativity/assets/57358478/4745a706-f66f-48a2-a046-0a483a926077">


### Conclusion
當三個模型在運行時，皆有表現出其特徵。而我認為 Combinational Creativity 為其中表現最好的。Exploratory Creativity 若能做到隨機排列效果會更好。而在 Transformational Creativity 中，從以上例子可以看到，在某些情況下，還是可以從其中看出原創作的影子。例如 content 顏色太鮮明造成 style  能影響的程度不高 。故若能真的實現改變圖片中的每個參數會更好，或是 content 中的元素若真的能被改變形狀而非僅侷限於大小上的改變，效果會更好。

### Reference
**[1]** *Computer Models of Creativity (Margaret A. Boden, 2009)*
**[2]** *Relating Cognitive Models of Design Creativity to the Similarity of Sketches Generated by an AI Partner (Pegah Karimi , Nicholas Davis , Mary Lou Maher , Kazjon Grace , Lina Lee, 2019)*
**[3]** *Neural Transfer Using PyTorch (colab)*
