[[AJACS蝦夷/講習内容]]へもどる

        --
目次

#contents
        --

# 自己紹介・かずさDNA研紹介 [#s204d1f4]

## 講師の中村 [#yb526cc0]

- 42歳。木更津市在住。

- こんな人です。
    -http://www.kazusa.or.jp/~yn/jp
    -http://catlover.myhome.cx/
    -http://twitter.com/catlover
    -http://mixi.jp/show_profile.pl?id=49640

- 京大→遺伝研→かずさと「ゲノム」と「情報」を扱ってきています。

## かずさDNA研究所 [#ma21de1d]

我が国初の大規模ゲノム塩基配列決定研究機関です。

- http://www.kazusa.or.jp/
    -シアノバクテリア http://bacteria.kazusa.or.jp/cyanobase/
    -根粒菌（共生窒素固定細菌) http://bacteria.kazusa.or.jp/rhizobase/
    -高等植物(シロイヌナズナ、ミヤコグサ、ユーカリ、トマト)

        --

# 【実習】検索サイトを使い倒そう [#jf20c376]

## google [#efc47312]

&color(green){ま、とにかく、まずは「ググれ」};

>Site: http://www.google.co.jp

### google は、なぜ検索できるのか [#l7e464ac]
- 「ロボット」もしくは「クローラー」がリンクをたどって収集にやってくる（以下はとあるかずさのWWWサーバのアクセスログにあったgooglebotの接続の痕跡）

 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:33:55 +0900] "GET /~yn/nekophoto/nekophoto-Thumbnails/82.jpg HTTP/1.1" 200 4612 "-" "Googlebot-Image/1.0"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:36:42 +0900] "GET /~yn/images/ika_kaidan.jpg HTTP/1.1" 200 25334 "-" "Googlebot-Image/1.0"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:37:01 +0900] "GET /~yn/jp/index.php?BusTable HTTP/1.1" 200 26037 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:51:15 +0900] "GET /~yn/jp/ HTTP/1.1" 200 15718 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:53:59 +0900] "GET /~yn/tdiary/images/ika_kaidan.jpg HTTP/1.1" 404 315 "-" "Googlebot-Image/1.0"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:03:03:44 +0900] "GET /~yn/jp/index.php?Genome2005Mac%2F2.BLAST HTTP/1.1" 200 23155 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
 ...

- つまり「どこからもリンクのないページ」は原理的に探索不可能
- どこかからリンクがあれば、いつかはやってくる
- 他のサイトからのリンクが多いほど、また、更新頻度が高いほど、上位にランクされる

- IE右上の虫眼鏡右にある三角をクリックして、検索先をLive SearchからGoogleに変えときましょう。
- 【課題】: スペース、ダブルコーテーションありなしの意味は？以下の検索結果を比較しましょう。ヒット数・検索結果がそれぞれ違います。

 北海道　大学　1,650,000件
 北海道大学　1,660,000件
 "北海道大学　1,350,000件
 "北海道　大学"　1,350,000件

- 規定値が「日本語のページを検索」になっていたら「検索オプション」から検索の対象にする言語を「すべての言語」に変えときましょう。

- スペースやダブルコーテーションを入れる場合、全角・半角で違いがありましたか？
- 実は、ダブルコーテーションを閉じる必要は''無い''、ということに気がつきましたか？
- ヒット数の違いが生じる理由を検索結果を参照しながら、考察しなさい

- 【解説】:
&color(white){単語を空白で分割して検索：OR検索が明示的にかかっている／ダブルコーテーションなし：自動的に「北海道」＋「大学」に分割された結果も混じるが、明示的に分ける程ではない／ダブルコーテーションで囲むと文字通りのフレイズで検索するのでもっともヒットが少ない（が、これも厳密ではなく、分割はされている。また、最後の例では、空白を無視している）};

- 【応用】: 遺伝子のアクセッション番号やID, 遺伝子名そのものでググる<br>
これが意外に使える。論文のサプリメントファイルが拾えたりする場合も。
- 【実習】：以下の記号はそれぞれどのような生物種のどのようなIDか。どのような情報が得られるか。ググれ

 sll1234
 LjT01C03

- 【実習】なにか酵素名でググれ (例: ATP transporter) どのようなサイトからどのような結果が得られるか

- 【応用】: 英文、とくに前置詞の使い方がただしいかどうか、ググる<br>
日本人の書いた文章がたくさんかかってくると、怪しいわけですよ。
- 【実習】:"Study on"でぐぐってみなさい

### 一歩すすんだ検索 [#i57b1c86]

&color(green){情報リテラシーを高めましょう};

- OR検索
googleはなにも指定しないと「AND 検索」つまり、キーワード全てを含むように検索します。<br>
キーワードのどちらか一部を含んでいればいい、といった検索「OR検索」には文字通り「OR」を使います。<br>

- 【実習】: 以下の検索の意味を考え、検索結果（特に右上の検索結果数) を比較しましょう。どのように違いますか？

 Xenopus tropicalis laevis
 Xenopus tropicalis OR laevis

- 【解説】:
&color(white){ 上：３つのキーワードが全部入っているページを検索 (91,600件) 下：Xenopusに加え、tropicalis か laevis の「どちらか」が記載されているページを検索 (2,720,000件)};<br>

- 【応用】：以下はそれぞれ、どのような検索をすることになるのでしょうか。その結果は？

 Xenopus OR tropicalis OR laevis
 "Xenopus tropicalis" OR "Xenopus laevis"

- 【解答】:
&color(white){ 上： 3つのうち、いずれかのキーワードがあればよいという、OR検索(10,300,000件)、下：「Xenopus tropicalis」または「Xenopus laevis」のどちらかのフレイズで検索(4,080,000)};<br>

- 【応用】：うっかり OR を小文字にしてしまいました。するとどのような結果が得られたでしょうか？orをいれないない場合と比較してみましょう。また、後ろにorをもってくるとどうかわりますか？

 Xenopus tropicalis or laevis
 Xenopus tropicalis laevis
 Xenopus tropicalis laevis or

- 【考察】:
&color(white){「or」のような短い頻出パターンも一応キーワードとして考慮されています。キーワードの入力順も検索の考慮の対象になっていますね。};<br>

- *  ワイルドカードを使ってみる<br>
なにが挟まっていても良いことを示す記号。トランプで言うと「ジョーカー」みたいなものです。以下を検索するとどのような文例が得られるでしょうか。''予測してから''実行しなさい。

 vitamin * is good for *

- ..  一定の数値範囲を指定

 Arabidopsis 2001..2006

//-【現在は利用できず】以前は以下のオプションで期間を指定することができた
//date:3, date:6, date12 - 期間指定
// cat genome date:3<br>
期間を明示的に検索したい場合、「検索オプション」で詳細に指定可能。

- -(マイナス)  キーワードを除外
キーワード「mouse」でイキモノのネズミの情報を検索するのはかなり困難だったりする。

 mouse
 mouse -パソコン -ホイール -ワイヤレス -アニメ

- filetype  filetype:ppt, filetype:pdf, filetype.doc, filetype:xls, filetype:txt, filetype:html<br>
ファイルタイプ指定 (Powerpoint, PDF, Word書類, Excel書類, text, html)

 blast filetype:ppt
 mouse filetype:xls

- site: inurl:  特定のサイト／URLで検索
以下はそれぞれ何を検索しようとしているかを考え、実際に検索してみて、検索数の違いを比較しましょう

 北海道大学
 北海道大学 site:hokudai.ac.jp
 北海道大学 -site:hokudai.ac.jp

    -【応用】：癌の研究に関係するPDF書類とプレゼンテーションを、文部科学省のサイトで探しなさい
    -【解答】：
&color(white){癌 研究 site:mext.go.jp filetype:pdf OR filetype:ppt};

    -【応用】：データベース統合に関係するPDF書類を、内閣府のサイトで探しなさい
    -【解答】：
&color(white){データベース統合 site:cao.go.jp filetype:pdf};

- link:  特定のサイトへのリンクがあるページ

 link:www.hokudai.ac.jp

//-電卓・通貨
//http://www.google.com/intl/ja/help/features.html#calculator <br>
//ちょっと便利だったりする。乗算はアスタリスク、アスタリスクが２つでべき乗。では以下を計算する方法は？
// 3x2
// 3の2乗
//--解答：&color(white){上：3*2　下 3**2 （3^2　でも可)};
//--応用：「8ルート3」の結果は何が得られると思いますか?
//--解答：&color(white){（8 かける（ルート３））の結果ですね};
//--応用：「8の3乗根」を求める方法は？
//--解答：&color(white){3th root of 8　どうやら日本語の表記法は無いようです};
//--「1000円を米ドルに」なんてのも可能

//**googleなその他のサーヴィスを使い倒す [#i21754f7]

//-マップ: http://maps.google.co.jp <br>
//学会逗留先の土地勘をつかむ。

//-カレンダー: http://www.google.com/calendar <br>
//ラボやらサークルの予定表共有に便利。iCal との連係も可能。

## 学術論文検索 [#i51588a0]

### [[PubMed:http://pubmed.gov]] [#fcf6673f]

&color(green){泣く子も黙るNational Center for Biotechnology Information (NCBI)提供の学術論文検索の総本山};

>Site: http://pubmed.gov (pubmed.org でも可)

E. coli O157のゲノム決定論文を探してみよう
++検索窓に E. coli と入れてGoをクリック<br>
Items of の数字が検索された数
++O157 を追加して「E. coli O157」で絞り込み検索する
++さらにgenomu を追加して「E. coli O157 genome」で検索する<br>
次第に絞り込まれ数が減少していく
++実際にどのようなタームに展開されて検索されているかは「Datails」タブをクリックするとわかる
++より一層の絞り込みは「Preview/Index」タブをクリックして指定するとよい。たとえば「Title/Abstract」や「Author」「Publication Date」に2001を指定するなどで絞りこめる

- 【課題】: 猫アレルギーの人が猫を飼うための猫洗いのテクニックを記述した学術論文を検索しなさい。(ヒント: wash allergy)<br>
- 【解答】:
&color(white){cat wash allergy で検索し「Evaluation of different techniques for washing cats: quantitation of allergen removed from the cat and the effect on airborne Fel d 1.」に至る。１週間に１度、３分間お湯につけるのを２回繰り返すとよい};

- 【応用】: RSS feedを使って、定点観測するには
    -本家統合TV: http://togotv.dbcls.jp/20070920.html ([[YouTube>http://www.youtube.com]]版: http://www.youtube.com/watch?v=5K8-xnkcClo ) を参照

- 【応用】: RSS feedを使えば、いろんなものの定点観測ができます。統合DBの成果物である[[KazusaNavigation>http://navi.kazusa.or.jp/]]を活用してみましょう。
    -植物系イヴェントのお知らせの定点観測用RSSは http://navi.kazusa.or.jp/plantevents/ の右ペインの「Community Forum」のアイコン
    -植物系人材募集を定点観測は http://navi.kazusa.or.jp/plantjob/ の右ペインの「Community Forum」のアイコンでどうぞ

- 【応用】: [[PubMed>http://pubmed.gov]]に収録されているすべての論文数を知りたい場合には？
    -本家: http://togotv.dbcls.jp/20071213.html ([[YouTube>http://www.youtube.com]]版: http://www.youtube.com/watch?v=Or5QeVMlzMQ ) を参照

### Google Scholar [#d86f1791]

&color(green){学術系のgoogle検索};

>Site: http://scholar.google.com

学術専門誌、論文、書籍、要約など、さまざまな分野の学術資料を検索。ISIと契約するお金がなくても、論文引用数の概数を知ることは可能。たとえば、Nakamura, Y. さんの発表論文や講演要旨をさがしてみよう。

 author:y-nakamura

y nakamura さん、多すぎです。所属である kazusa を追加してみよう。

 author:y-nakamura kazusa

- 【課題】: y-nakamura さんが、かずさに来てから12年間に発表した論文のなかで、いちばん引用されてるのはどれだろうか。

- 【課題】: あなたの論文、あるいはあなたの知り合いの先生の論文で一番引用されているのはどれだろうか。たとえば、どんな論文からそれが引用されているだろうか。調べなさい。

- 【課題】: BLAST ( basic local alignment search tool ) の初出論文を引用している論文数は膨大なモノだと考えられるが、その数を調べ、また、引用している論文を列挙しなさい
- 【解答】:
&color(white){basic local alignment search tool で検索し、引用元を確認};<br>
文献管理ソフトであるBibTeXやEndnoteに取り込むためのファイルダウンロードが可能。see. 検索オプション


// ***[[OReFiL:an Online Resource Finder for Lifesciences>http://orefil.dbcls.jp/]] [#y58530dd]
// &color(green){ライフサイエンス分野の文献に記載されているウェブリソース(データベースやツールなど)を検索するならこれ};
// 統合TV: http://togotv.dbcls.jp/20070831.html ([[YouTube>http://www.youtube.com]]版: http://jp.youtube.com/watch?v=gF1wyc9SF8Q ) を参照して、使い倒そう！
// -【課題】: codon usage をアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べなさい
// -【課題】: primerをアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べなさい


        --
[[AJACS蝦夷/講習内容]]へもどる
