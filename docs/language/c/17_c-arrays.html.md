<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 数组</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">数组</span></h1>&#13;
&#13;
<p>C 语言支持<b>数组</b>数据结构，它可以存储一个固定大小的相同类型元素的顺序集合。数组是用来存储一系列数据，但它往往被认为是一系列相同类型的变量。</p>&#13;
&#13;
<p>数组的声明并不是声明一个个单独的变量，比如 runoob0、runoob1、...、runoob99，而是声明一个数组变量，比如 runoob，然后使用 runoob[0]、runoob[1]、...、runoob[99] 来代表一个个单独的变量。</p>&#13;
<p>所有的数组都是由连续的内存位置组成。最低的地址对应第一个元素，最高的地址对应最后一个元素。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/09/c-arrays-2021-1-18-3.png" alt="C 中的数组"/></p>&#13;
<p>数组中的特定元素可以通过索引访问，第一个索引值为 <span class="marked">0</span>。</p><p>C 语言还允许我们使用指针来处理数组，这使得对数组的操作更加灵活和高效。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/09/c-array-2021-01-18-2.png"/></p>&#13;
&#13;
&#13;
<h2 class="tutheader">声明数组</h2>&#13;
<p>在 C 中要声明一个数组，需要指定元素的类型和元素的数量，如下所示：</p>&#13;
<pre>&#13;
type arrayName [ arraySize ];&#13;
</pre>&#13;
<p>这叫做一维数组。<b>arraySize</b> 必须是一个大于零的整数常量，<b>type</b> 可以是任意有效的 C 数据类型。例如，要声明一个类型为 double 的包含 10 个元素的数组 <b>balance</b>，声明语句如下：</p>&#13;
<pre>&#13;
double balance[10];&#13;
</pre>&#13;
<p>现在 <i>balance</i> 是一个可用的数组，可以容纳 10 个类型为 double 的数字。</p>&#13;
&#13;
<h2 class="tutheader">初始化数组</h2>&#13;
<p>在 C 中，您可以逐个初始化数组，也可以使用一个初始化语句，如下所示：</p>&#13;
<pre>&#13;
double balance[5] = {1000.0, 2.0, 3.4, 7.0, 50.0};&#13;
</pre>&#13;
<p>大括号 { } 之间的值的数目不能大于我们在数组声明时在方括号 [ ] 中指定的元素数目。</p>&#13;
<p>如果您省略掉了数组的大小，数组的大小则为初始化时元素的个数。因此，如果：</p>&#13;
<pre>&#13;
double balance[] = {1000.0, 2.0, 3.4, 7.0, 50.0};&#13;
</pre>&#13;
<p>您将创建一个数组，它与前一个实例中所创建的数组是完全相同的。下面是一个为数组中某个元素赋值的实例：</p>&#13;
<pre>&#13;
balance[4] = 50.0;&#13;
</pre>&#13;
<p>上述的语句把数组中第五个元素的值赋为 50.0。所有的数组都是以 0 作为它们第一个元素的索引，也被称为基索引，数组的最后一个索引是数组的总大小减去 1。以下是上面所讨论的数组的的图形表示：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/09/c-arrays-2021-1-18-4.png" alt="数组表示"/></p>&#13;
<p>下图是一个长度为 <strong>10</strong> 的数组，第一个元素的索引值为 <strong>0</strong>，第九个元素 <strong>runoob</strong> 的索引值为 <strong>8</strong>:</p>&#13;
<img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/09/c-array-2021-01-18-2.png"/>&#13;
<h2 class="tutheader">访问数组元素</h2>&#13;
<p>数组元素可以通过数组名称加索引进行访问。元素的索引是放在方括号内，跟在数组名称的后边。例如：</p>&#13;
<pre>&#13;
double salary = balance[9];&#13;
</pre>&#13;
<p>上面的语句将把数组中第 10 个元素的值赋给 salary 变量。下面的实例使用了上述的三个概念，即，声明数组、数组赋值、访问数组：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">n</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-number">10</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code">; </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> n 是一个包含 10 个整数的数组 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">,</span><span class="hl-identifier">j</span><span class="hl-code">;
 
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 初始化数组元素 </span><span class="hl-mlcomment">*/</span><span class="hl-code">         
   </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">10</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">n</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">i</span><span class="hl-code"> + </span><span class="hl-number">100</span><span class="hl-code">; </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 设置元素 i 为 i + 100 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 输出数组中每个元素的值 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">j</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code"> &lt; </span><span class="hl-number">10</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Element[%d] = %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">j</span><span class="hl-code">, </span><span class="hl-identifier">n</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div></div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Element[0] = 100&#13;
Element[1] = 101&#13;
Element[2] = 102&#13;
Element[3] = 103&#13;
Element[4] = 104&#13;
Element[5] = 105&#13;
Element[6] = 106&#13;
Element[7] = 107&#13;
Element[8] = 108&#13;
Element[9] = 109&#13;
</pre>&#13;
<h2 class="tutheader">获取数组长度</h2>&#13;
<p>数组长度可以使用 <strong>sizeof</strong> 运算符来获取数组的长度，例如：</p>&#13;
<pre>int numbers[] = {1, 2, 3, 4, 5};&#13;
int length = sizeof(numbers) / sizeof(numbers[0]);</pre>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> array<span style="color: #008000;">[</span><span style="color: #008000;">]</span> <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> length <span style="color: #000080;">=</span> <span style="color: #05a;">sizeof</span><span style="color: #008000;">(</span>array<span style="color: #008000;">)</span> <span style="color: #000040;">/</span> <span style="color: #05a;">sizeof</span><span style="color: #008000;">(</span>array<span style="color: #008000;">[</span><span style="color: #0000dd;">0</span><span style="color: #008000;">]</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">printf</span><span style="color: #008000;">(</span><span style="color: #a11;">"数组长度为: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span>, length<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>使用宏定义：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #060;">#define LENGTH(array) (sizeof(array) / sizeof(array[0]))</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> array<span style="color: #008000;">[</span><span style="color: #008000;">]</span> <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> length <span style="color: #000080;">=</span> LENGTH<span style="color: #008000;">(</span>array<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">printf</span><span style="color: #008000;">(</span><span style="color: #a11;">"数组长度为: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span>, length<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>以上实例输出结果为：</p>&#13;
<pre>数组长度为: 5</pre>&#13;
&#13;
<h2 class="tutheader">数组名</h2><p>&#13;
在 C 语言中，数组名表示数组的地址，即数组首元素的地址。当我们在声明和定义一个数组时，该数组名就代表着该数组的地址。</p>&#13;
<p>&#13;
例如，在以下代码中：</p>&#13;
<pre>&#13;
int myArray[5] = {10, 20, 30, 40, 50};</pre><p>&#13;
在这里，myArray 是数组名，它表示整数类型的数组，包含 5 个元素。myArray 也代表着数组的地址，即第一个元素的地址。</p><p>数组名本身是一个常量指针，意味着它的值是不能被改变的，一旦确定，就不能再指向其他地方。</p>&#13;
<p>&#13;
我们可以使用&amp;运算符来获取数组的地址，如下所示：</p>&#13;
<pre>&#13;
int myArray[5] = {10, 20, 30, 40, 50};&#13;
int *ptr = &amp;myArray[0]; // 或者直接写作 int *ptr = myArray;</pre><p>&#13;
在上面的例子中，ptr 指针变量被初始化为 myArray 的地址，即数组的第一个元素的地址。</p>&#13;
<p>&#13;
需要注意的是，虽然数组名表示数组的地址，但在大多数情况下，数组名会自动转换为指向数组首元素的指针。这意味着我们可以直接将数组名用于指针运算，例如在函数传递参数或遍历数组时：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #993333;">void</span> printArray<span style="color: #000;">(</span><span style="color: #993333;">int</span> arr<span style="color: #000;">[</span><span style="color: #000;">]</span><span style="color: #339933;">,</span> <span style="color: #993333;">int</span> size<span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #708;">for</span> <span style="color: #000;">(</span><span style="color: #993333;">int</span> i <span style="color: #339933;">=</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span> i <span style="color: #339933;">&lt;</span> size<span style="color: #339933;">;</span> i<span style="color: #339933;">++</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
        <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"%d "</span><span style="color: #339933;">,</span> arr<span style="color: #000;">[</span>i<span style="color: #000;">]</span><span style="color: #000;">)</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 数组名arr被当作指针使用</span><br/>
    <span style="color: #000;">}</span><br/>
<span style="color: #000;">}</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #993333;">int</span> myArray<span style="color: #000;">[</span><span style="color: #164;">5</span><span style="color: #000;">]</span> <span style="color: #339933;">=</span> <span style="color: #000;">{</span><span style="color: #164;">10</span><span style="color: #339933;">,</span> <span style="color: #164;">20</span><span style="color: #339933;">,</span> <span style="color: #164;">30</span><span style="color: #339933;">,</span> <span style="color: #164;">40</span><span style="color: #339933;">,</span> <span style="color: #164;">50</span><span style="color: #000;">}</span><span style="color: #339933;">;</span><br/>
    printArray<span style="color: #000;">(</span>myArray<span style="color: #339933;">,</span> <span style="color: #164;">5</span><span style="color: #000;">)</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 将数组名传递给函数</span><br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div><p>&#13;
在上述代码中，printArray 函数接受一个整数数组和数组大小作为参数，我们将 myArray 数组名传递给函数，函数内部可以像使用指针一样使用 arr 数组名。</p>&#13;
<h2 class="tutheader">C 中数组详解</h2>&#13;
<p>在 C 中，数组是非常重要的，我们需要了解更多有关数组的细节。下面列出了 C 程序员必须清楚的一些与数组相关的重要概念：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:30%">概念</th><th>描述</th></tr>&#13;
<tr><td> <a href="/cprogramming/c-multi-dimensional-arrays.html" title="C 中的多维数组">多维数组</a></td><td>C 支持多维数组。多维数组最简单的形式是二维数组。</td> </tr>&#13;
<tr><td> <a href="/cprogramming/c-passing-arrays-to-functions.html" title="C 中传递数组给函数作为参数">传递数组给函数</a></td><td>您可以通过指定不带索引的数组名称来给函数传递一个指向数组的指针。</td> </tr>&#13;
<tr><td> <a href="/cprogramming/c-return-arrays-from-function.html" title="C 中从函数返回数组">从函数返回数组</a></td><td>C 允许从函数返回数组。</td> </tr>&#13;
<tr><td> <a href="/cprogramming/c-pointer-to-an-array.html" title="C 中指向数组的指针">指向数组的指针</a></td><td>您可以通过指定不带索引的数组名称来生成一个指向数组中第一个元素的指针。</td> </tr>&#13;
<tr><td> <a href="/cprogramming/c-static-dynamic-array.html" title="C 语言静态数组与动态数组">静态数组与动态数组</a></td><td>静态数组在编译时分配内存，大小固定，而动态数组在运行时手动分配内存，大小可变。</td> </tr>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>