# Handling pushback in code reviews (處理code reviews中的反饋,處理反對意見或應對阻力)



Sometimes a developer will push back on a code review. Either they will disagree
with your suggestion or they will complain that you are being too strict in
general.

有時候，開發人員會對程式碼審查提出反對意見。 他們可能會不同意您的建議，或者抱怨您過於嚴格。 

## Who is right? (誰是對的？) {#who_is_right}

When a developer disagrees with your suggestion, first take a moment to consider
if they are correct. Often, they are closer to the code than you are, and so
they might really have a better insight about certain aspects of it. Does their
argument make sense? Does it make sense from a code health perspective? If so,
let them know that they are right and let the issue drop.  

當開發人員不同意您的建議時，請先花點時間考慮他們是否正確。 通常，他們比您更接近程式碼，因此他們可能確實對某些方面有更好的洞察力。 他們的論點是否有道理？ 從程式碼健康的角度來看是否有意義？ 如果是這樣，請讓他們知道他們是對的，並讓這個問題過去。  

> 筆記：  
> 在程式碼審查過程中，保持開放的心態的重要性。 審查者應該尊重開發人員的專業意見，並願意承認自己的錯誤。 如果開發人員的論點合理且符合程式碼健康原則，審查者應該欣然接受並放下自己的堅持。  

However, developers are not always right. In this case the reviewer should
further explain why they believe that their suggestion is correct. A good
explanation demonstrates both an understanding of the developer's reply, and
additional information about why the change is being requested.

然而，開發人員並不總是正確的。 在這種情況下，審查者應該進一步解釋為什麼他們認為自己的建議是正確的。 一個好的解釋既要表明對開發人員回覆的理解，又要提供有關為何要求進行此更改的更多資訊。  
>  筆記：
>  1. 在 code reviews 中，審查者不僅要提出自己的意見，還需要能夠清楚地解釋和論證自己的觀點，以說服開發人員並促進有效的溝通。
>  2. 提供更多關於為何要求進行此更改的資訊，例如：
>     *  符合團隊的程式碼風格指南
>     *  提高程式碼的可讀性、可維護性或可測試性
>     *  避免潛在的問題或風險
>     *  符合系統的設計原則  


In particular, when the reviewer believes their suggestion will improve code
health, they should continue to advocate for the change, if they believe the
resulting code quality improvement justifies the additional work requested.
**Improving code health tends to happen in small steps.**

特別是，當 reviewer 認為他們的建議將改善程式碼健康狀況時，如果他們認為所得到的程式碼品質改進證明了所要求的額外工作是合理的，則他們應該繼續倡導該更改。  
** 程式碼健康的提升往往需要一點一滴地累積 **
> 筆記：
> 在 code reviews 中，reviewer 對於提升程式碼品質的責任。 如果 reviewer 認為某個修改對於提升程式碼健康狀況至關重要，即使開發人員有不同的意見， reviewer 也應該繼續堅持自己的觀點，並向開發人員充分解釋修改的必要性和重要性。  
> **  需要注意的是 **  : 即使 reviewer 認為自己的建議是正確的，也應該保持禮貌和尊重，避免與開發人員發生爭執。 溝通和協商是解決程式碼審查中分歧的關鍵。  

Sometimes it takes a few rounds of explaining a suggestion before it really
sinks in. Just make sure to always stay [polite](comments.md#courtesy) and let
the developer know that you *hear* what they're saying, you just don't *agree*.  

有時需要經過幾輪解釋才能讓對方真正理解您的建議。 只要確保始终保持 有禮貌 的態度，並讓開發人員知道您 有聽見 他們的意見，只是您 不同意 而已。  

## Upsetting Developers (讓開發人員不滿、讓開發者心煩意亂 ) {#upsetting_developers}

Reviewers sometimes believe that the developer will be upset if the reviewer
insists on an improvement. Sometimes developers do become upset, but it is
usually brief and they become very thankful later that you helped them improve
the quality of their code. Usually, if you are [polite](comments.md#courtesy) in
your comments, developers actually don't become upset at all, and the worry is
just in the reviewer's mind. Upsets are usually more about
[the way comments are written](comments.md#courtesy) than about the reviewer's
insistence on code quality.

reviewer 有時會認為，如果他們堅持某項改進，開發人員會感到不滿。 開發人員確實偶爾會不高興，但通常這種情緒很快就會消退，並且之後會因為你幫助他們提升了程式碼品質而非常感謝你。 一般來說，只要你的評論 禮貌，開發人員通常根本不會感到不滿，這種擔憂往往只是 reviewer 自己心裡想的。 不滿通常更多地與 評論的撰寫方式 有關，而不是審查者堅持程式碼品質所致。  


## Cleaning It Up Later ( 稍後再清理 ) {#later}

A common source of push back is that developers (understandably) want to get
things done. They don't want to go through another round of review just to get
this CL in. So they say they will clean something up in a later CL, and thus you
should LGTM *this* CL now. Some developers are very good about this, and will
immediately write a follow-up CL that fixes the issue. However, experience shows
that as more time passes after a developer writes the original CL, the less
likely this clean up is to happen. In fact, usually unless the developer does
the clean up *immediately* after the present CL, it never happens. This isn't
because developers are irresponsible, but because they have a lot of work to do
and the cleanup gets lost or forgotten in the press of other work. Thus, it is
usually best to insist that the developer clean up their CL *now*, before the
code is in the codebase and "done." Letting people "clean things up later" is a
common way for codebases to degenerate.  

開發人員常會提出的一種反對意見是，他們（可以理解地）希望完成工作。 他們不想再進行另一輪審查只是為了提交這個 CL。 因此，他們會說稍後會清理某些東西，因此您現在應該 LGTM 這個 CL。 有些開發人員在這方面做得很好，並會立即編寫後續的 CL 來修復該問題。 然而，經驗表明，隨著開發人員編寫原始 CL 後的時間越長，這種清理發生的可能性就越小。 事實上，通常除非開發人員在當前 CL 之後立即 進行清理，否則它永遠不會發生。 這並不是因為開發人員不負責任，而是因為他們有很多工作要做，而清理工作在其他工作的壓力下迷失或被遺忘。 因此，通常最好堅持要求開發人員 現在 清理他們的 CL，在程式碼進入程式碼庫並「完成」之前。 允許人們「稍後再清理」是程式碼庫退化的常見方式。  

>  筆記：
>  在程式碼審查中，不應該輕易允許開發人員以「稍後再清理」為由，而放過一些程式碼問題。 因為經驗表明，如果開發人員沒有立即進行清理，這些問題很可能永遠得不到解決，最終導致程式碼庫的品質下降。
>
> 建議:  
>  1. 審查者應該堅持要求開發人員在提交 CL 之前，儘可能地完善程式碼，包括處理一些小的問題和改進。  
>  2. 如果開發人員確實需要將某些清理工作放在後續的 CL 中，應該明確地記錄下來，並確保這些後續的 CL 儘快得到提交。  


If a CL introduces new complexity, it must be cleaned up before submission
unless it is an [emergency](../emergencies.md). If the CL exposes surrounding
problems and they can't be addressed right now, the developer should file a bug
for the cleanup and assign it to themselves so that it doesn't get lost. They
can optionally also write a TODO comment in the code that references the filed
bug.

提交程式碼變更 (CL) 之前，必須先清除所有會引入新複雜性的部分，除非是緊急情況 emergency。如果此 CL 暴露了周圍的程式碼問題，且這些問題無法立即解決，開發人員應自行建構一個紀錄此清理工作的漏洞 (bug)，並將其指派给自己，以避免遗漏。他們還可以選擇在程式碼中新增一個 TODO 註釋，並引用現有的漏洞編號。  

>  筆記：
>  在提交程式碼變更之前，確保程式碼的可維護性和避免引入額外的複雜性。
>  如果發現了需要修復的程式碼問題，但無法立即著手，應該透過適當的流程 (例如建構漏洞) 將其記錄下來，以便日後追蹤和處理。


## General Complaints About Strictness ( 關於嚴格審查的常見抱怨  ) {#strictness}

If you previously had fairly lax code reviews and you switch to having strict
reviews, some developers will complain very loudly. Improving the
[speed](speed.md) of your code reviews usually causes these complaints to fade
away.

如果以前您的程式碼審查標準比較寬鬆，突然轉變為嚴格的審查，一些開發人員可能會提出强烈的抱怨。 提高程式碼審查的 速度 通常可以緩解這些抱怨。  

>  筆記：  
>  當程式碼審查標準突然提高時，一些開發人員可能會感到不適應而提出抱怨。 但是，如果能夠提高程式碼審查的效率，讓審查過程更加快速，通常可以緩解這些抱怨。
>  建議:
>  1. 審查者應該在提高標準的同時，也注重審查效率的提升。例如，可以簡化審查流程、使用適當的審查工具等等。
>  2. 可以與開發團隊進行溝通，解釋提高審查標準的原因和好處，並尋求大家的理解和配合。

Sometimes it can take months for these complaints to fade away, but eventually
developers tend to see the value of strict code reviews as they see what great
code they help generate. Sometimes the loudest protesters even become your
strongest supporters once something happens that causes them to really see the
value you're adding by being strict.

有時這些抱怨可能需要幾個月才會消失，但最終開發人員往往會看到嚴格的程式碼審查的價值，因為他們會看到這些審查如何幫助他們生成優秀的程式碼。 有時，最激烈的抗議者甚至會成為您最強大的支持者，一旦發生某些事情，使他們真正看到您通過嚴格審查所增加的價值。  

>  筆記：
> 雖然一開始可能會遇到一些阻力，但堅持嚴格的程式碼審查最終會帶來好處。 當開發人員親身體驗到嚴格審查的好處後，他們往往會成為最堅定的支持者。
>  建議:
>  1. 審查者應該耐心、堅持地進行嚴格的程式碼審查，並向開發人員解釋和說明嚴格審查的意義和價值。  
>  2. 團隊可以通過舉辦分享會、交流會等方式，讓開發人員了解嚴格審查的好處，並分享成功案例。  

## Resolving Conflicts ( 解決衝突 )  {#conflicts}

If you are following all of the above but you still encounter a conflict between
yourself and a developer that can't be resolved, see
[The Standard of Code Review](standard.md) for guidelines and principles that
can help resolve the conflict.

如果您遵循了上述所有準則，但仍然遇到您和開發人員之間無法解決的衝突，請參閱 [The Standard of Code Review] 以獲取有助於解決衝突的準則和原則。    
> 解釋：
> 這段文字提供了解決程式碼審查中衝突的途徑。
> 首先建議遵循前面提到的準則，例如保持禮貌的溝通、解釋您的觀點、堅持程式碼品質等等。
> 如果溝通仍然無法解決問題，則建議參考另一份文件 [The Standard of Code Review]。該文件可能包含更詳細的準則和流程，用於處理難以達成共識的複雜情況。

