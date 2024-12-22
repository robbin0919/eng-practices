# How to write code review comments ( 如何撰寫 code review 評論 )



## Summary ( 摘要  )

-   Be kind.( 友善一點。 )
-   Explain your reasoning. ( 解釋你的推理、理由 )
-   Balance giving explicit directions with just pointing out problems and
    letting the developer decide. ( 在給予明確指示與僅指出問題並讓開發人員決定之間取得平衡。 )
-   Encourage developers to simplify code or add code comments instead of just
    explaining the complexity to you. ( 鼓勵開發人員簡化程式碼或添加程式碼註釋，而不是僅僅向您解釋複雜性。 )

## Courtesy ( 禮貌 )

In general, it is important to be
[courteous and respectful](https://chromium.googlesource.com/chromium/src/+/master/docs/cr_respect.md)
while also being very clear and helpful to the developer whose code you are
reviewing. One way to do this is to be sure that you are always making comments
about the *code* and never making comments about the *developer*. You don't
always have to follow this practice, but you should definitely use it when
saying something that might otherwise be upsetting or contentious. For example:

一般而言，在審查他人的程式碼時，保持禮貌和尊重，同時也要清楚、有幫助地向開發人員提供意見是很重要的。 一種實現這一點的方法是確保您的評論始終針對程式碼本身，而不是針對開發人員。您不一定總是需要遵循這個做法，但當您要說一些可能引起不悅或爭議的話時，絕對應該使用這種方式。例如：


Bad: "Why did **you** use threads here when there's obviously no benefit to be
gained from concurrency?"

不佳的範例： "你為什麼要在這裡使用線程？顯然從concurrency（並發性）中得不到任何好處。"

Good: "The concurrency model here is adding complexity to the system without any
actual performance benefit that I can see. Because there's no performance
benefit, it's best for this code to be single-threaded instead of using multiple
threads."

較佳的範例： "目前的concurrency（並發性）模型增加了系統的複雜性，但卻沒有看到任何實際的性能提升。由於沒有性能優勢，因此最好將此程式碼改為單線程，而不是使用多個線程。"

> 筆記：
>
> 更委婉: "在這個情況下使用線程似乎沒有帶來任何並發性的優勢，您能否說明一下這樣設計的原因呢?"  
> 解釋:  
> 這個句子直接指責開發人員使用了不必要的線程，可能會引起開發人員的不悅。  
> 更委婉的翻譯則以疑問的方式提出，更加尊重開發人員的專業判斷，同時也表達了對程式碼設計的疑問。  
> 建議:  
> 在程式碼審查過程中，儘量使用委婉、建設性的語言，避免直接指責或批評開發人員。   
 

## Explain Why ( 解釋為什麼 ) {#why}

One thing you'll notice about the "good" example from above is that it helps the
developer understand *why* you are making your comment. You don't always need to
include this information in your review comments, but sometimes it's appropriate
to give a bit more explanation around your intent, the best practice you're
following, or how your suggestion improves code health.

關於上面的「較佳的範例」，您會注意到的一件事是，它可以幫助開發者理解您發表評論的原因。您並不總是需要在審閱意見中包含此信息，但有時適當地對您的意圖、遵循的最佳實踐或建議，如何改善程式碼健康狀況提供更多解釋。 

## Giving Guidance ( 給予引導 ) {#guidance}

**In general it is the developer's responsibility to fix a CL, not the
reviewer's.** You are not required to do detailed design of a solution or write
code for the developer.

**一般來說，修復 CL 是開發人員的責任，而不是審閱者的責任。**  您不需要為開發人員進行解決方案的詳細設計或編寫程式碼。

This doesn't mean the reviewer should be unhelpful, though. In general you
should strike an appropriate balance between pointing out problems and providing
direct guidance. Pointing out problems and letting the developer make a decision
often helps the developer learn, and makes it easier to do code reviews. It also
can result in a better solution, because the developer is closer to the code
than the reviewer is.

但這並不意味著審稿人應該沒有幫助。一般來說，您應該在指出問題和提供直接指導之間取得適當的平衡。
指出問題並讓開發人員做出決定通常可以幫助開發人員學習、並使程式碼審查變得更容易。它還可以產生更好的解決方案，因為開發人員比審查人員更接近程式碼。 

However, sometimes direct instructions, suggestions, or even code are more
helpful. The primary goal of code review is to get the best CL possible. A
secondary goal is improving the skills of developers so that they require less
and less review over time.
 
然而，有時直接的指示、建議、甚至程式碼會更有幫助。code review 的主要目標是獲得盡可能最好的 CL。次要個目標是提高開發人員的技能，以便隨著時間的推移，他們需要的審查越來越少。

Remember that people learn from reinforcement of what they are doing well and
not just what they could do better. If you see things you like in the CL,
comment on those too! Examples: developer cleaned up a messy algorithm, added
exemplary test coverage, or you as the reviewer learned something from the CL.
Just as with all comments, include [why](#why) you liked something, further
encouraging the developer to continue good practices.
 
請記住，人們透過強化自己做得好的事情來學習，而不僅僅是他們可以做得更好的事情。 如果您在 CL 中看到您喜歡的內容，也請發表評論！範例：開發人員清理了混亂的演算法，添加了示例性測試覆蓋率，或者您作為審閱者從 CL 中學到了一些東西。就像所有評論一樣，包括[為什麼](#為什麼)你喜歡某些東西，進一步鼓勵開發人員繼續良好的實踐。

## Label comment severity ( 標籤評論嚴重性 ) {#label-comment-severity}

Consider labeling the severity of your comments, differentiating required
changes from guidelines or suggestions.
 
考慮標記您的評論的嚴重性，將所需的更改與指南或建議區分開來。

Here are some examples:

> Nit: This is a minor thing. Technically you should do it, but it won’t hugely
> impact things.  
>這是個小問題。技術上來說你應該這樣做，但不會對整體產生重大影響。  
>可以理解為一個微小的瑕疵，雖然應該修正，但不會造成嚴重後果.  
> 
> Optional (or Consider): I think this may be a good idea, but it’s not strictly
> required.  
> 我認為這可能是一個好主意，但不是強制要求的。  
> 可以理解為一個建議，可以採納也可以不採納，視情況而定。  
>
> FYI: I don’t expect you to do this in this CL, but you may find this
> interesting to think about for the future.  
> 我不期望你在這個變更列表 (CL) 中處理這個，但你可能覺得未來考慮這個很有趣。  
> 可以理解為提供一些額外的資訊，供開發者參考，但不屬於當前需要處理的範圍。  
> 



This makes review intent explicit and helps authors prioritize the importance of
various comments. It also helps avoid misunderstandings; for example, without
comment labels, authors may interpret all comments as mandatory, even if some
comments are merely intended to be informational or optional.
 
這使得評論意圖明確，並幫助作者優先考慮各種評論的重要性。它還有助於避免誤解；例如，如果沒有評論標籤，作者可能會將所有評論解釋為強制性的，即使某些評論只是為了提供資訊或可選。  


>筆記：
> 在程式碼審查中，Nit、Optional (或 Consider)、FYI 這三個詞通常用來標記不同類型的評論，它們分別代表：  
> Nit (小問題)  
> 定義： 指的是程式碼中一個微小的、不影響程式功能，但可能影響可讀性、一致性或未來維護性的細節。例子：
>  * 缺少分號  
>  * 命名不一致
>  * 空白格使用不規範
>  * 註解不夠清楚
>  特徵： 雖然是小問題，但累積起來會影響程式碼的整體品質。主要關注程式碼的細節和風格。
>  可能會寫下以下評論 : 這行應該加一個空格。  
>  
>  Optional (或 Consider，建議考慮)
> 定義： 指的是一個可以改進程式碼的建議，但不是必須的。例子：
> * 可以用更簡潔的寫法  
> * 可以使用更好的演算法
> * 可以增加錯誤處理
> * 可以添加註解來解釋某段複雜的邏輯
> 特徵： 這類建議可以提高程式碼的效率、可讀性或健壯性，但不是必須的，開發者可以根據情況自行決定是否採納。提供改進的建議，但不是強制性的。
> 可能會寫下以下評論 : 可以考慮使用字典來存儲這些數據，會更方便查找。    
>
> FYI (For Your Information，供參考)  
> 定義： 指的是一些額外的資訊，供開發者參考，但不一定需要立即採取行動。例子：
> * 這個函式在其他地方也有使用
> * 這個變數的值可能會在未來改變
> * 這個功能在特定情況下可能會出現問題
>  特徵： 這類資訊可以幫助開發者更好地理解程式碼，但可能不直接影響當前的修改。 提供額外的資訊，供開發者參考。
>  可能會寫下以下評論 : 這個函式在處理大數據集時可能會比較慢，可以考慮優化。  


## Accepting Explanations ( 接受解釋 ) {#explanations}

If you ask a developer to explain a piece of code that you don't understand,
that should usually result in them **rewriting the code more clearly**.
Occasionally, adding a comment in the code is also an appropriate response, as
long as it's not just explaining overly complex code.

如果您要求開發人員解釋一段您不理解的程式碼，通常會導致他們更清楚地重寫程式碼。有時，在程式碼中加入註解也是一種適當的回應，只要它不只是解釋過於複雜的程式碼。

**Explanations written only in the code review tool are not helpful to future
code readers.** They are acceptable only in a few circumstances, such as when
you are reviewing an area you are not very familiar with and the developer
explains something that normal readers of the code would have already known.  

**僅在程式碼審查工具中編寫的解釋對未來的程式碼讀者沒有幫助。**
它們僅在少數情況下是可接受的，例如當您正在審查您不太熟悉的領域並且開發人員解釋了程式碼的普通讀者已經知道的內容時。

Next: [Handling Pushback in Code Reviews](pushback.md)
