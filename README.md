# IForgot
<h1><img class="alignnone  wp-image-99" src="https://catmaoblog.files.wordpress.com/2016/10/6lqz4de.png" alt="Icon made by Freepik from www.flaticon.com" width="40" height="40" /> <a href="https://catmao1230.github.io/IForgot/" target="_blank">點我前往</a></h1>
<h1><img class="alignnone  wp-image-99" src="https://catmaoblog.files.wordpress.com/2016/10/6lqz4de.png" alt="Icon made by Freepik from www.flaticon.com" width="40" height="40" /> <a href="https://catmaoblog.wordpress.com/2016/10/10/iforgot/" target="_blank">WordPress</a></h1>
<h1><img class="alignnone  wp-image-94" src="https://catmaoblog.files.wordpress.com/2016/10/jjbk5s5.png" alt="Icon made by Vectors Market from www.flaticon.com" width="40" height="40" /> 玩法解說</h1>
畫面中總共有八張卡片，上三下五，上排為題目，下排為答題區。

<img class="alignnone size-full wp-image-96" src="https://catmaoblog.files.wordpress.com/2016/10/hgz2v7b.png" alt="hgz2v7b" width="1137" height="627" />

一開始上排會顯示題目，玩家須記下圖片順序，幾秒後題目會覆蓋，玩家依序選擇答案。

<img class="alignnone size-full wp-image-97" src="https://catmaoblog.files.wordpress.com/2016/10/bkzt0yr.png" alt="bkzt0yr" width="1137" height="627" />

答題三次失敗則遊戲結束。
<h1><img class="alignnone  wp-image-43" src="https://catmaoblog.files.wordpress.com/2016/10/ril6i6c.png" alt="Icon made by flaticon from www.flaticon.com" width="40" height="40" /> 程式碼</h1>
這個遊戲主要的程式是在於題目的亂數，需要產生不重複的三個亂數，我採用了洗牌法。
<ol>
	<li>假設現在有一個陣列，大小為 6 ，一開始先依序存入 A、B、C、D、E、F ，上方數字為陣列 index 。<img class="alignnone size-full wp-image-102" src="https://catmaoblog.files.wordpress.com/2016/10/4yl58jm.png" alt="4yl58jm" width="767" height="309" /></li>
	<li>用亂數取兩個 0 ~ 5 的值，決定兩張要交換的 index ，交換後如下圖，兩張牌只有內容改變， index 不變。
<img class="alignnone size-full wp-image-103" src="https://catmaoblog.files.wordpress.com/2016/10/cukworo.png" alt="cukworo" width="767" height="251" /></li>
	<li>再度用亂數取兩個 0 ~ 5 的值，做交換。
<img class="alignnone size-full wp-image-104" src="https://catmaoblog.files.wordpress.com/2016/10/q5bpiwp.png" alt="q5bpiwp" width="767" height="309" />
<img class="alignnone size-full wp-image-105" src="https://catmaoblog.files.wordpress.com/2016/10/qqa9byd.png" alt="qqa9byd" width="767" height="251" /></li>
	<li>多交換幾次後，就可以得到一個不重複的亂數，此為洗牌法。<img class="alignnone size-full wp-image-106" src="https://catmaoblog.files.wordpress.com/2016/10/nr5ajc7.png" alt="nr5ajc7" width="767" height="251" /></li>
</ol>
程式碼如下：
<pre><code>string Array[6]={"A", "B", "C", "D", "E", "F"};
int index1, index2;
string temp;
for(int i = 0; i < 100; i++){ // 代表交換了 100 次
	index1 = rand() % 6; // 0 ~ 5
	index2 = rand() % 6;

	// 兩者內容交換
	temp = Array[index1];
	Array[index1] = Array[index2];
	Array[index2] = temp;
}</code></pre>
<h1><img class="alignnone  wp-image-42" src="https://catmaoblog.files.wordpress.com/2016/10/tpodion.png" alt="tpodion" width="40" height="40" /> 遊戲素材</h1>
<ul class="alt">
	<li><a href="http://opengameart.org/users/tokyogeisha" target="_blank">TokyoGeisha / Open Game Art</a></li>
</ul>
<h1><img class="alignnone  wp-image-42" src="https://catmaoblog.files.wordpress.com/2016/10/tpodion.png" alt="tpodion" width="40" height="40" /> 參考資料</h1>
<ul class="alt">
	<li><a href="https://coder.tw/?p=532" target="_blank">洗牌演算法（交換法） / 碼人日誌</a></li>
	<li><a href="https://kelunyang.wordpress.com/2009/04/01/javascript%E7%9A%84poker%E6%BC%94%E7%AE%97%E6%B3%95%EF%BC%88%E7%99%BC%E4%BA%82%E6%95%B8%E4%B8%8D%E9%87%8D%E8%A4%87%EF%BC%89/" target="_blank">JavaScript的shuffle演算法 / 南史氏言</a></li>
</ul>
