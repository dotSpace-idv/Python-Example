使用 Markdown 標記語法的心得
===========================

簡介
----
[**Markedown**](https://zh.wikipedia.org/wiki/Markdown)是一種輕量級的標記語言，於 2004 年由[**約翰‧格魯伯(John Gruber)**](https://zh.wikipedia.org/wiki/%E7%B4%84%E7%BF%B0%C2%B7%E6%A0%BC%E9%AD%AF%E4%BC%AF)及[**亞倫‧斯沃茨(Aaron Swartz)**](https://zh.wikipedia.org/wiki/%E4%BA%9A%E4%BC%A6%C2%B7%E6%96%AF%E6%B2%83%E8%8C%A8)所共同合作而創造出的成果。其目的，是希望人們用慣用的方式來寫作，而非困惑於 HTML 這類的方式來表達文章。也就是用易讀易寫的純文字方式來寫文章，並經由 Markedown 這套工具把純文字轉換成有效的 XHTML (或是 HTML)。

Markdown 是格魯伯用 [**Perl**](https://zh.wikipedia.org/wiki/Perl) 這個程式語言所寫作而成的， 其是 (1) **一種語法** （2) **一個把純文字轉化成 HTML 格式的軟體工具**。接下來，我只會針對 Github 在運用 Markedown 方面的語法做說明，並展示以範例。

語法說明及實作範例
-----------------
### 標題(Headings)
可以在文字的開頭加上 1 至 6 個「井字符號」(像是：\#標題文字)，這對應到 HTML 的 H1 至 H6 的標記標籤(tag)。例如：

```
# H1 標題一
## H2 標題二
### H3 標題三
#### H4 標題四
##### H5 標題五
###### H6 標題六
```

如此 Markedown 會轉換成：

# H1 標題一
## H2 標題二
### H3 標題三
#### H4 標題四
##### H5 標題五
###### H6 標題六

當然，也可以在標題文字的下一行加上「等於符號」或「減號」，來對應到 HTML 的 H1 或 H2 的標記標籤。如下列的方式：

```
H1 標題一
=========

H2 標題二
---------
```

轉換的結果如下：

H1 標題一
=========

H2 標題二
---------

兩種方式可以擇一而為，當然也可以混合使用。

### 樣式(Styling text)
有時要強調某些文字或句子，像是粗體或斜體，則就必須運用到這些語法。

|樣式|語法|範例|輸出結果|
|----|:--:|:----|:----|
|粗體|** ** 或 __ __|\*\*這是粗體字\*\*|**這是粗體字**|
|斜體|* * 或 _ _|\*這是斜體字\*|*這是斜體字*|
|刪除|~~ ~~|\~\~這是錯誤的文字\~\~|~~這是錯誤的文字~~|
|粗斜體|** ** 和 _ _|\*\*\_這段文字很重要\_\*\*|**_這段文字很重要_**|

如果使用中文，建議不要使用粗斜體，除非你整個句子都要使用這樣的格式。如果要在整個句子裡使用粗斜體強調部分文字，例如：

```
如果使用中文，**_建議不要使用粗斜體_**，除非你整段都要使用這樣的格式。
```
則顯示為：

如果使用中文，**_建議不要使用粗斜體_**，除非你整段都要使用這樣的格式。

這樣是可以的，但若是「建議不要使用粗斜體」僅「不要使用」使用粗斜體，而其他的為粗體，那麼：

```
如果使用中文，**建議_不要使用_粗斜體**，除非你整段都要使用這樣的格式。
```
就會顯示成：

如果使用中文，**建議_不要使用_粗斜體**，除非你整段都要使用這樣的格式。

這顯示的結果不是我們要的，問題在於在使用斜體樣式符號(_)的前後都要加上空白，文字不能連一塊。要正確顯示就必須改為：

```
如果使用中文，**建議 _不要使用_ 粗斜體**，除非你整段都要使用這樣的格式。
```
如此會顯示成：

如果使用中文，**建議 _不要使用_ 粗斜體**，除非你整段都要使用這樣的格式。

但這樣的結果很突兀。若是英文句子，字與字之前本來就要空格，所以不會覺得奇怪，然而中文字的字裡行間並不需要空格，才會顯得不合理。如果你真的有需要在一個句子裡，把部分文字顯示成粗斜體，中文就必須採取**內嵌 HTML** (Inline HTML)的作法。

```
 如果使用中文，<b>建議<i>不要使用</i>粗斜體</b>，除非你整段都要使用這樣的格式。
```
這樣一來結果會是：

如果使用中文，<b>建議<i>不要使用</i>粗斜體</b>，除非你整段都要使用這樣的格式。


### 引用文字(Quoting text)

### 引用程式碼(Quoting code)

### 鏈結(Links)

### 章節鏈結(Section links)

### 相對鏈結(Relative links)

### 清單(Lists)

### 作業清單(Task lists)

### 有關人員及團隊的議題(Mentioning people and teams)

### 引用問題和拉出需求Referencing issues and pull requests

### 使用表情文字(Using emoji)

### 段落和換行(Paragraphs and line breaks)

### 把 Markedown 的格式忽略掉(Ignoring Markdown formatting)
有時我們需要顯示 \#、 \* 等符號，如此就必須告知 Markdown 把它的標記符號忽略掉，我們可以在這些符號的前面加上**反斜線**(\)，表達我們要正常顯示這些符號。例如：

```
我想把\*\*這些符號\*\*正常顯示出來，而不經由 **Markdown** 轉換。
```

以上會顯示成：

我想把\*\*這些符號\*\*正常顯示出來，而不經由 **Markdown** 轉換。


參考資料
--------
1. [Markdown 官方網站](https://daringfireball.net/projects/markdown/)。
2. [Markdown Cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)。
3. [Github 在 Markedown 應用方面的說明](https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/)。
4. [Markdown 語法說明(中文翻譯文件)](http://markdown.tw/)。
5. [Markdown - 自由軟體鑄造場](https://www.openfoundry.org/tw/resourcecatalog/Program-Development/Markup-Languages/markdown)。
