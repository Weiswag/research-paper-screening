# Research Paper Screening

一個協助篩選研究文獻的 Codex Skill。它先查核期刊是否有掠奪性出版或冒名風險，再使用 **CRAAP** 架構分析單篇論文，提出「納入、待查或排除」的建議。

## 評估內容

### 1. 期刊可信度

查核期刊名稱、ISSN、出版社、同儕審查方式、編委資訊、收費與出版倫理政策，並交叉確認期刊宣稱的資料庫收錄情況。

單一跡象不會直接被當成掠奪性期刊的證據。例如，收取版面費、採開放取用模式，或未被某個資料庫收錄，都不足以單獨下結論。

### 2. CRAAP 分析

| 面向 | 評估重點 |
| --- | --- |
| **Currency 時效性** | 出版日期、更新或勘誤，以及是否符合研究領域的時效需求 |
| **Relevance 相關性** | 論文是否回答研究問題、符合納入條件 |
| **Authority 權威性** | 作者專長、機構、期刊與同儕審查資訊 |
| **Accuracy 準確性** | 方法、資料、分析與結論是否有足夠證據支持 |
| **Purpose 目的** | 研究目的、資助、利益衝突與可能的立場偏向 |

評估結果會區分已查證的事實、推論與尚未確認的資訊，不會把五項分數簡單相加來決定論文品質。

## 安裝

將整個 `research-paper-screening` 資料夾放入 Codex 的 skills 目錄：

- Windows：`%USERPROFILE%\.codex\skills\research-paper-screening`
- macOS／Linux：`~/.codex/skills/research-paper-screening`

資料夾結構：

```text
research-paper-screening/
├── SKILL.md
└── agents/
    └── openai.yaml
```

## 使用方式

在 Codex 中輸入：

> 請用 `$research-paper-screening` 評估這篇論文是否適合納入我的研究。  
> 研究問題：[你的研究問題]  
> 論文 DOI 或連結：[DOI／網址]

也可以提供論文 PDF、研究範圍，以及既定的納入／排除條件。

## 輸出結果

Skill 會提供：

1. **納入／待查／排除**的暫定建議及主要理由
2. 期刊可信度查核結果
3. CRAAP 五項分析
4. 尚需確認的資訊
5. 查核日期與可追溯的來源連結

如果只提供摘要，Skill 會標明無法完整審查研究方法。期刊有疑點但證據不足時，結果會列為「待查」，不會直接宣稱該期刊具有掠奪性。

## 參考依據

- [CSU Chico Meriam Library：CRAAP Test](https://library.csuchico.edu/sites/default/files/craap-test.pdf)
- [Think. Check. Submit.：Journals Checklist](https://thinkchecksubmit.org/journals/)
- [COPE／DOAJ／OASPA／WAME：Principles of Transparency and Best Practice in Scholarly Publishing](https://doaj.org/apply/transparency/)

## 注意

這個 Skill 用於輔助文獻篩選。最終是否納入研究，仍應依你的研究問題、預先設定的篩選條件，以及可取得的論文全文判斷。
