## **1.1 动词**
  
动词代表了我们打算对文本进行什么操作。例如：

-   d 删除 delete
-   r 替换 [replace](https://www.zhihu.com/search?q=replace&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1733228460%7D)
-   c 修改 change
-   y 复制 yank
-   v 选取 [visual select](https://www.zhihu.com/search?q=visual%20select&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1733228460%7D)
  
## **1.2 名词**  
名词代表了我们即将处理的文本。Vim 中有一个专门的术语叫做[文本对象](https://www.zhihu.com/search?q=%E6%96%87%E6%9C%AC%E5%AF%B9%E8%B1%A1&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1733228460%7D)text object，示例：

-   w 单词word
-   s sentence
-   p 段落paragraph
-   t HTML标签tag
-   引号或者各种括号所包含的文本称作一个文本块。
  
## **1.3 介词

介词界定了待编辑文本的范围或者位置。例如：

-   i “在…之内”inside
-   a “环绕…”around
-   t “到…位置前”to
-   f “到…位置上”[forward](https://www.zhihu.com/search?q=forward&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1733228460%7D)

  
## **1.4 组词为句**
  
[文本编辑](https://www.zhihu.com/search?q=%E6%96%87%E6%9C%AC%E7%BC%96%E8%BE%91&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1733228460%7D)命令的基本语法如下：  
**动词+介词+名词**  
例子:

-   删除一个段落 delete inside paragraph: dip
-   选取一个句子 visual select inside sentence: vis
-   修改一个单词 change inside word: ciw
-   修改一个单词 change around word: caw
-   删除文本直到字符“x”（不包括字符“x”）delete to x: dtx
-   删除文本直到字符“x”（包括字符“x”）delete forward x: dfx

  
## **1.5 数词**
  
数词指定了待编辑文本对象的数量, 语法就成了这样：  
**动词+介词/数词+名词**  
例子：

-   修改三个单词 change three words: c3w
-   删除两个单词 delete two words: d2w

另外，数词也可以修饰动词，表示将操作执行 n 次。语法：  
**数词+动词+名词**  
示例：

-   两次删除单词（等价于删除两个单词） [twice delete word](https://www.zhihu.com/search?q=twice%20delete%20word&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A1733228460%7D): 2dw
-   三次删除字符（等价于删除三个字符）three times delete character: 3x