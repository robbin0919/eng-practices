# The Standard of Code Review （ code review 的標準 )



The primary purpose of code review is to make sure that the overall
code health of Google's code
base is improving over time. All of the tools and processes of code review are
designed to this end.

code review 的主要目的是確保 Google 程式碼庫的整體程式碼健康狀況隨著時間推移而持續改善。所有 code review 的工具和流程都是為了實現這個目標而設計的。

> * 程式碼健康狀況 (code health)： 泛指程式碼的品質，包括可讀性、可維護性、可測試性、性能、安全性等方面。  
> * 程式碼庫 (code base)： 指一個軟體專案中所有源程式碼的集合。  
> 這段話強調了程式碼審查的核心價值：提升程式碼品質，確保軟體系統的長期可維護性和穩定性。  

In order to accomplish this, a series of trade-offs have to be balanced.  
為了實現這個目標，必須平衡一系列的權衡取捨。  
> 在程式碼審查過程中，需要在不同因素之間進行平衡，例如：  
> * 速度與品質: 快速審查可能導致遺漏問題，而過於嚴格的審查可能會降低開發效率。  
> * 自動化與人工審查: 自動化工具可以提高效率，但無法完全取代人工審查。  
> * 個人風格與團隊標準: 允許個人風格可以提高創造力，但統一的風格可以提高可讀性和維護性。  
因此，在實踐中需要根據實際情況，找到一個最佳的平衡點。   

First, developers must be able to _make progress_ on their tasks. If you never
submit an improvement to the codebase, then the codebase never improves. Also,
if a reviewer makes it very difficult for _any_ change to go in, then developers
are disincentivized to make improvements in the future.   
首先，開發人員必須能夠推進他們的任務。如果從不提交對程式碼庫的改進，那麼程式碼庫就不會進步。此外，如果審查人員使得任何更改都很難通過，那麼開發人員將失去未來做出改進的動力。

> 解釋：  
> make progress： 翻譯為「推進」，強調開發人員在工作進度上的持續前進。  
> disincentivized： 翻譯為「失去動力」，指開發人員由於審查過程過於嚴格或困難，而感到沮喪或失去改進程式碼的積極性。  
> 這段話強調了程式碼審查的目標之一是促進程式碼的持續改進，因此需要在審查過程中保持合理的平衡，既要保證程式碼品質，又要鼓勵開發人員積極提交改進。  

On the other hand, it is the duty of the reviewer to make sure that each CL is
of such a quality that the overall code health of their codebase is not
decreasing as time goes on. This can be tricky, because often, codebases degrade
through small decreases in code health over time, especially when a team is
under significant time constraints and they feel that they have to take
shortcuts in order to accomplish their goals.

另一方面，審查人員有責任確保每個 CL（Change List）的品質，以防止程式碼庫的整體健康狀況隨著時間的推移而下降。這可能很棘手，因為程式碼庫通常會隨著時間的推移而逐漸降低健康狀況，尤其是在團隊承受著巨大的時間壓力，並且他們覺得必須採取捷徑來實現目標的情況下。  

> 解釋:  
> CL (Change List)： 指程式碼變更集，即一次提交的一組程式碼修改。  
> code health： 程式碼健康狀況，如前面解釋，是指程式碼的品質，包括可讀性、可維護性、可測試性、性能、安全性等方面。  
> degrade： 逐漸惡化、退化。  
> 這段話強調了審查人員在維護程式碼庫健康狀況方面的責任。即使開發人員面臨時間壓力，審查人員也應該堅持一定的品質標準，避免短期的捷徑導致長期的負面影響。  

Also, a reviewer has ownership and responsibility over the code they are
reviewing. They want to ensure that the codebase stays consistent, maintainable,
and all of the other things mentioned in
["What to look for in a code review."](looking-for.md)

此外，審查人員對他們正在 code review 擁有權限和責任。他們希望確保程式碼庫保持一致性、可維護性，以及「 code review 中應關注的事項」中提到的所有其他方面。  

> 解釋:  
> ownership and responsibility： 翻譯為「擁有權限和責任」，強調審查人員在程式碼品質方面扮演的重要角色。  
> consistent： 一致的，指程式碼風格、命名規則、設計模式等方面的一致性。  
> maintainable： 可維護的，指程式碼易於理解、修改和擴展。  
> "What to look for in a code review."： 指程式碼審查中應關注的事項，例如可讀性、正確性、性能、安全性、可測試性等。  
> 這段話進一步強調了審查人員在維護程式碼庫品質方面的責任。他們不僅僅是發現問題，更應該積極參與到程式碼的改進過程中，確保程式碼庫符合團隊的標準和要求。  

Thus, we get the following rule as the standard we expect in code reviews:

**In general, reviewers should favor approving a CL once it is in a state where
it definitely improves the overall
code health of the system
being worked on, even if the CL isn't perfect.**

因此，我們得到以下規則作為我們在程式碼審查中所期望的標準：  
一般而言，審查人員應該傾向於批准一個 CL，只要它處於 顯著改善正在開發的系統的整體程式碼健康狀況 的狀態，即使該 CL 尚未完美。  

> 解釋:  
> CL (Change List)： 程式碼變更集，即一次提交的一組程式碼修改。  
> code health： 程式碼健康狀況，如前面解釋，是指程式碼的品質，包括可讀性、可維護性、可測試性、性能、安全性等方面。  
> 這段話強調了程式碼審查的最終目標：提升系統的整體程式碼健康狀況。
> 
> 在實際審查過程中，審查人員應該以這個目標為導向，重點關注 CL 是否對系統的整體健康狀況有顯著的提升，而不是過於糾結於一些細枝末節的完美主義。

That is _the_ senior principle among all of the code review guidelines.
那是所有程式碼審查指南中最重要的原則。  

There are limitations to this, of course. For example, if a CL adds a feature
that the reviewer doesn't want in their system, then the reviewer can certainly
deny approval even if the code is well-designed.

當然，這也有其局限性。例如，如果一個 CL 添加了審查人員不希望在其系統中出現的功能，那麼審查人員當然可以拒絕批准，即使程式碼設計良好。  

> 解釋:  
> the senior principle： 強調這個原則在所有程式碼審查指南中的重要性和優先級。  
> limitations： 局限性，指這個原則並非在所有情況下都絕對適用。  
> 這段話說明了雖然「提升系統的整體程式碼健康狀況」是最重要的原則，但並非絕對的。審查人員仍有權力根據專案的需求和目標，對 CL 進行合理的拒絕。  

A key point here is that there is no such thing as "perfect" code&mdash;there is
only _better_ code. Reviewers should not require the author to polish every tiny
piece of a CL before granting approval. Rather, the reviewer should balance out
the need to make forward progress compared to the importance of the changes they
are suggesting. Instead of seeking perfection, what a reviewer should seek is
_continuous improvement_. A CL that, as a whole, improves the maintainability,
readability, and understandability of the system shouldn't be delayed for days
or weeks because it isn't "perfect."

關鍵點在於，不存在「完美」的程式碼——只有「更好」的程式碼。 審查人員不應該要求作者在批准之前將 CL 的每個小細節都拋光。相反，審查人員應該平衡前進的需要與他們所建議的更改的重要性。 審查人員應該追求的是「持續改進」，而不是追求完美。 一個整體上提高了系統的可維護性、可讀性和可理解性的 CL 不應該因為不「完美」而被延誤幾天或幾週。
> 解釋：  
> * "perfect" code： 完美程式碼，強調不存在絕對完美的程式碼。  
> * polish： 拋光，比喻對程式碼進行細微的調整和改進。  
> * continuous improvement： 持續改進，強調程式碼品質的逐步提升，而非一次性達到完美。  
> 這段話強調了程式碼審查的重點應該是促進程式碼的持續改進，而不是追求理想化的「完美」。過度追求完美可能會阻礙開發進度，降低團隊的工作效率。  

Reviewers should _always_ feel free to leave comments expressing that something
could be better, but if it's not very important, prefix it with something like
"Nit: " to let the author know that it's just a point of polish that they could
choose to ignore.

Note: Nothing in this document justifies checking in CLs that definitely
_worsen_ the overall code health of the system. The only time you would do that
would be in an [emergency](../emergencies.md).

## Mentoring

Code review can have an important function of teaching developers something new
about a language, a framework, or general software design principles. It's
always fine to leave comments that help a developer learn something new. Sharing
knowledge is part of improving the code health of a system over time. Just keep
in mind that if your comment is purely educational, but not critical to meeting
the standards described in this document, prefix it with "Nit: " or otherwise
indicate that it's not mandatory for the author to resolve it in this CL.

## Principles {#principles}

*   Technical facts and data overrule opinions and personal preferences.

*   On matters of style, the [style guide](http://google.github.io/styleguide/)
    is the absolute authority. Any purely style point (whitespace, etc.) that is
    not in the style guide is a matter of personal preference. The style should
    be consistent with what is there. If there is no previous style, accept the
    author's.

*   **Aspects of software design are almost never a pure style issue or just a
    personal preference.** They are based on underlying principles and should be
    weighed on those principles, not simply by personal opinion. Sometimes there
    are a few valid options. If the author can demonstrate (either through data
    or based on solid engineering principles) that several approaches are
    equally valid, then the reviewer should accept the preference of the author.
    Otherwise the choice is dictated by standard principles of software design.

*   If no other rule applies, then the reviewer may ask the author to be
    consistent with what is in the current codebase, as long as that doesn't
    worsen the overall code health of the system.

## Resolving Conflicts {#conflicts}

In any conflict on a code review, the first step should always be for the
developer and reviewer to try to come to consensus, based on the contents of
this document and the other documents in
[The CL Author's Guide](../developer/index.md) and this
[Reviewer Guide](index.md).

When coming to consensus becomes especially difficult, it can help to have a
face-to-face meeting or a video conference between the reviewer and the author, instead of
just trying to resolve the conflict through code review comments. (If you do
this, though, make sure to record the results of the discussion as a comment on
the CL, for future readers.)

If that doesn't resolve the situation, the most common way to resolve it would
be to escalate. Often the
escalation path is to a broader team discussion, having a Technical Lead weigh in, asking
for a decision from a maintainer of the code, or asking an Eng Manager to help
out. **Don't let a CL sit around because the author and the reviewer can't come
to an agreement.**

Next: [What to look for in a code review](looking-for.md)
