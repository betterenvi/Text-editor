<h3>Simple Text Editor</h3>

<p>程序运行环境：需要在linux下运行，并确保安装了libncurses库，若无此库请先安装（Ubuntu下执行sudo apt-get install libncurses5-dev)</p>

<p>编译链接: 在终端打开此文件夹，执行g++ -o editor screen.cpp main.cpp cursor.cpp text.cpp -lncurses，即可生成editor可执行文件</p>

<p>操作说明：</p>

<h5>一，启动程序：</h5>

<p>基本语法 ./editor -option file</p>
<p>选项又-e（进入编辑模式），-o（进入只读模式），可不加选项（进入程序会有提示）</p>
<p>file为任一已存在的文本，本文件夹中提供了测试文本news1.txt, news2.txt, empty.txt</p>

<h5>二，基本操作：</h5>

<p>本编辑器可实现的基本操作有：</p>
<ol>
<li>光标移动：
<ul>
	<li>h , j , k , l分别代表左，下，右，上，同时也可以使用方向键</li>
	<li>数字n+（hjkl或方向键）表示向指定方向移动n个位置</li>
	<li>0，HOME键表示移动到逻辑行行首，$，END键表示移动到逻辑行行尾</li>
	<li>（表示移动到文本的开头，）表示移动到文本的结尾</li>
	<li>w表示移动到下一个单词的开始（以空格键的分割表示一个单词），W表示移动到上一个单词的末尾。</li>
	<li>数字n+G表示移动到文本的第n个逻辑行，n+$表示移动到当前逻辑行的第n列。</li>
	<li>BACKSPACE键表示左移一位</li>
	<li>鼠标点击光标到点击位置，若该位置无文本，则移动到改行的最后一个字符处。</li>
</ul>
</li>
<li>翻页操作
<ul>
	<li>ctrl+[UDFB],意思分别是U（上一整页），D（下一整页），F（向下半页），B（向上半页），同时也可使用pgup，pgdown键，分别具有crtl+U与ctrl+D的功能</li>
</ul>
</li>
<li>插入功能（仅在编辑模式下有效）
<ul>
	<li>按i/I/o/O/a/A进入插入模式，实现方式与Vim相同，同时INSERT键与i有相同的作用</li>
	<li>进入插入模式可以插入任意字符，按esc键退出插入模式。</li>
</ul>
</li>
<li>删除功能（仅在编辑模式下有效）
<ul>
	<li>x，delete键删除光标所在字符，D表示删除当前行</li>
	<li>d（数字n）[hjkl],hl表示向光标左右删除连续（n+1）个字符（包括光标所在位置），jk表示从光标所在行向上（下）删除n行</li>
</ul>
<li>搜索与替换
<ul>
	<li>/与？进入搜索模式，根据提示输入所需要搜索的字符，按回车后会在屏幕中高亮所要寻找的字符，同时光标移动到先前位置后（前）第一个出现该字符的位置。</li>
	<li>搜索后可使用按键n或N向指定方向搜索下一个（上一个）出现该字符的位置。若指定方向已无所需字符串会有提示。</li>
	<li>一般模式下按s进入全文替换模式，根据提示输入替换和被替换字符串，按回车后会将全文中的被替换字符串替换成新字符串。</li>
	<li>按F2键或者ctrl+L键清除高亮</li>
	<li>可搜索通配符</li>
</ul>
<li>保存与退出
<ul>
	<li>按ctrl+S键保存，按q键退出（不保存）</li>
</ul>
<li>末行提示
<ul>
	<li>在一般模式下和插入模式下，末行会提示当前光标所在的逻辑行以及所在列，当用户输入有误时会输出Invalid Operation，在搜索模式下，末行会指引用户进行输入，在保存时末行也会输出确认了的信息。</li>
</ul>
</ol>

<h5>三，注意事项：</h5>

<p>使用本文本编辑器需要注意以下几点，可能也是本编辑器还未完善的地方</p>
<ul>
	<li>在终端开启编辑器后请勿改变终端窗口的大小，在开启编辑器前可任意改变，编辑器会自动识别窗口的大小</li>
	<li>请勿编辑或阅读不存在的文本</li>
	<li>一次只能编辑一个文件</li>
	<li>不要删除文本最后的空字符（非空字符没有关系）</li>
	<li>空文本首次插入请使用i键</li>
</ul>

