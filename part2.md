[[AJACS蝦夷/講習内容]]へもどる

        --
目次

#contents
        --

# 塩基配列決定プロジェクトとは [#ob9a3488]

## ゲノムとは [#cb6f531c]
- 「ome」は「総体」を示す接尾辞
    -遺伝子 gene の全体像が gene+ome=genome「ゲノム」
    -ほかには transcriptome, proteome, interactome, phenome などなど
    -こうした網羅的な研究群を「オーミクス omics 」という
    -geneの総体であるgenomeを全部とりつくそうってのが genome sequencing project
- omics のなかでの genome の位置＝最下層＝基盤 infrastructure ＝縁の下の力持ち

## シークエンシング [#s6017426]
- 蛍光によるdideoxy法~
[[図：DNAの鎖の伸長:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p13-1.8.jpg]]~
[[図：１塩基（ヌクレオチド）の違いを見分ける電気泳動:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p179-6.1.jpg]]~
[[図：dideoxy法による塩基配列決定法(1):http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p180-6.2.jpg]]~
[[図：dideoxy法による塩基配列決定法(2):http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/DNAp140.jpg]]~
[[図：蛍光dideoxy法による自動塩基配列決定:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p185-6.7.jpg]]~


## かずさのゲノム塩基配列決定プロジェクト [#i2957229]
- 光合成 photosynthesis と窒素固定 nitrogen fixation に着目して

## 配列決定戦略 [#mb47f09b]
- クローンバイクローン clone by clone 法~
クローン毎に、小分けにしてから
- ショットガン shotgun 法~
全ゲノムをばらばらにして、再構成 (assemble)

## ゲノムの構成 [#g8208c04]
[[図：ゲノムの比較:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p36-2.2.jpg]]~
生物種によって違う

### 原核生物（真性細菌と古細菌） [#t1db4988]
[[図：大腸菌の核様体:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p55-2.18.jpg]]~
- 塩基配列のほとんどの領域はタンパク質遺伝子

### 真核生物 [#g7bd98d7]
[[図：ヒト染色体:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p43-2.8.jpg]]~
[[図：ヒトゲノムの構成:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p25-B1.4.jpg]]~
- 塩基配列の多くは繰り返し配列
- エクソン＝イントロン構造
//-ほとんどは無駄な領域と言われてきた → 7割が機能？
- ゲノムデータベース~
    -http://www.ensembl.org/
<br>など

        --

# 【実習】配列情報データベースへのアクセス [#t4eb1c1f]

## Entrez [#y974888c]

&color(green){配列に関連した情報を何でも引けるNational Center for Biotechnology Information (NCBI)の生物系検索決定版};

>http://www.ncbi.nlm.nih.gov/Entrez/

- Boolean Operators
    -AND: To ‘AND’ two search terms together instructs Entrez to find all documents that contain BOTH terms
    -OR: To ‘OR’ two search terms together instructs Entrez to find all documents that contain EITHER term.
    -NOT: To ‘NOT’ two search terms together instructs Entrez to find all documents that contain search term 1 BUT NOT search term 2.<br>
<br>
- 【実習】: 以下の手順で検索を実行しなさい
    -Entrezをひらき、眺める（大量のデータベースの複合体であることに注意）
    -"interleukin-2" で検索してみる
    -AND human を追加して絞ってみる ("interleukin-2" AND human で検索)
    -AND cDNA
    -AND Taniguchi<br>
などでしぼりこみ、NucleotideのACCESSION: J00264 のデータに到達する。
    -それぞれのFeatures（からのリンク）を確認しよう。

- 【実習】:  以下の２つの検索語の意味を考えてから、Entrezを検索しなさい。結果の違いに注目。
    -g1p3 AND (response element OR promoter)
    -g1p3 AND response element OR promoter


## GOLD [#v749521b]

&color(green){世界中のゲノムプロジェクトとESTプロジェクトを網羅したすごいテーブル};

>http://www.genomesonline.org

- 【実習】: それぞれのカテゴリにどれだけの数のプロジェクトがあるか、また、どのような生物のプロジェクトがあるかを確認しなさい
    -終了したプロジェクト published
    -進行中の古細菌プロジェクト ongoing archaea
    -進行中の原核生物プロジェクト ongoing bacteria
    -進行中の真核生物プロジェクト ongoing eukaryotes
    -メタゲノムプロジェクト（複数の生物をまとめて読んでしまうやりかた） metagenomes<br>
<br>
- 学名で書かれているのでわからん！と言うヒトは
    -いきなりgoogleとかで学名検索しても、もちろんいいんですよ~

- 【実習】猫の学名は？

- 【実習】GOLDで「ネコゲノムプロジェクト」について調べてみましょう。どのカテゴリにありますか？
    -どんな組織が実行？
    -データは公開されているか？
    -で、なんでまた、猫ゲノム？

- 【応用】: 猫の遺伝子は国際DNAデータバンクにいくつ登録されているか？(Entrezで検索しましょう)

- 【実習】: あなたが使っている、興味のある生物種のゲノム／ESTプロジェクトはないか、GOLDやEntrezで調べてみよう


## NCBI Taxonomy [#h9d32d6b]

&color(green){生物分類と配列情報を関連させて調べたい場合にはここ};

>http://www.ncbi.nlm.nih.gov/sites/entrez?db=Taxonomy

- 【実習】: 猫の系統 (liniage) を閲覧し、各々の階層での類縁の生物を確認しよう
- 【実習】: 猫の配列データはどのくらい蓄積されているか？
- 【実習】: 猫の研究論文はどのくらいあるか？

- 【実習】: あなたが使っている、興味のある生物種について、同様にNCBI Taxonomyで調べてみよう


## [[CyanoBase>http://bacteria.kazusa.or.jp/cyanobase]] [#h374fa76]

&color(green){光合成細菌シアノバクテリアゲノムデータの世界中心};

>http://bacteria.kazusa.or.jp/cyanobase/

- 【実習】: シアノバクテリア '''Synechocystis''' sp. PCC 6803株のゲノム情報はどのように提供されているか
    -典型的なバクテリアゲノム（環状構造）をもつPCC 6803の図
    -典型的なゲノムデータベースとしてのcyanobaseの構成とは(keyword search, BLAST search, functional category etc.)

        --

# 類似配列の検索法 [#h9a93537]

[[図：配列アラインメント（塩基配列）:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p541-16.8.jpg]]~
[[図：配列アラインメント（タンパク質＝アミノ酸の配列）:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/B5.jpg]]~
[[図：配列アラインメントのためのドットプロット:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/p541-16.9.jpg]]~
[[図：ドットプロット(1):http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/Bp171.jpg]]~
[[図：ドットプロット(2):http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/Bp172.jpg]]~
[[図：ドットプロットの方法(1):http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/Bp169-4.1.jpg]]~
[[図：ドットプロットの方法(2):http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/Bp176-4.1.jpg]]~
//[[図：ドットプロットからのアラインメント例:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/Bp218-4.6.jpg]]~
//[[図：ドットプロットからのアラインメント例:http://charles.kazusa.or.jp/~yn/pukiwiki/lecture/tmu2007/images/Bp218-4.6.jpg]]~

//**アミノ酸配列のアラインメント [#f7b2516b]
//***「マトリクス」＝類似の程度を示す [#j18f41ca]
//-PAM250
//-BLOSUM62

### ダイナミックプログラミング = DP [#x4c57fc6]
- 「最適経路中の部分経路もまた最適経路になっている」
- 動的計画法は、この原理を利用して最適化問題を解く。
- ある問題を、多段階に「バラす」ことができる場合、動的計画法によって各段階の最適解(経路)を求め、それをたどることで、全体の問題を解くことが可能になる。

### まじめにDPやるとタイヘンなんで、はしょる [#if9f71f7]
- FASTA
    -よく似た領域の周囲だけをDPで探索
- BLAST
    -「ワード」の一致を発見
    -そこからアラインメントを横へ伸ばす。伸びなくなったらあきらめる。
    -きわめて高速で巨大配列も探索可能
- BLAST検索のprogram option
|program|Query|DB|概要|
|BLASTN|核酸配列|核酸配列|問い合わせ配列と類似の核酸配列を検索|
|BLASTP|アミノ酸配列|アミノ酸配列|問い合わせ配列と類似のアミノ酸配列を検索|
|BLASTX|核酸配列|アミノ酸配列|問い合わせ核酸配列をアミノ酸に翻訳した配列で、類似のアミノ酸配列を検索|
|TBLASTN|アミノ酸配列|核酸配列|アミノ酸配列を核酸配列のデータベースを翻訳したものと類似の配列を検索|
|TBLASTX|核酸配列|核酸配列|問い合わせ核酸配列を全フレーム翻訳したものを、核酸配列データベースを全フレーム翻訳したものとの類似を検索|
|PSI-BLAST|アミノ酸配列|アミノ酸配列|問い合わせ配列とアミノ酸データベースとの検索を繰り返すことで、弱い類似しかない配列を検索可能にする方法|
|PHI-BLAST|アミノ酸配列|アミノ酸配列|配列の「パターン」で類似の配列を検索する|

        --

# 【実習】BLASTあれこれ [#ha03692c]

&color(green){配列検索のホームラン王};

    -統合TV本家: http://togotv.dbcls.jp/20070808.html
([[YouTube>http://www.youtube.com]]版: http://www.youtube.com/watch?v=RaI8gWye79U ) を参照

>http://www.ncbi.nlm.nih.gov/blast/

アミノ酸配列のBLASTを実行してみましょう。

- 「protein BLAST」を選択
- 「Search」窓に以下の配列をコピペする (cmd-C then cmd-V)

// >opsin Rh2(Drosophila melanogaster)
 MERSHLPETPFDLAHSGPRFQAQSSGNGSVLDNVLPDMAHLVNPYWSRFAPMDPMMSKIL
 GLFTLAIMIISCCGNGVVVYIFGGTKSLRTPANLLVLNLAFSDFCMMASQSPVMIINFYY
 ETWVLGPLWCDIYAGCGSLFGCVSIWSMCMIAFDRYNVIVKGINGTPMTIKTSIMKILFI
 WMMAVFWTVMPLIGWSAYVPEGNLTACSIDYMTRMWNPRSYLITYSLFVYYTPLFLICYS
 YWFIIAAVAAHEKAMREQAKKMNVKSLRSSEDCDKSAEGKLAKVALTTISLWFMAWTPYL
 VICYFGLFKIDGLTPLTTIWGATFAKTSAVYNPIVYGISHPKYRIVLKEKCPMCVFGNTD
 EPKPDAPASDTETTSEADSKA

- 「Choose database」で「swissprot」を選択
- 「BLAST」ボタンをクリック<br>
- 解析の待ち時間の間、The Conserved Domain Database (CDD)  が表示される
- 画像の7tm_1をクリック<br>
conserved domainとして「pfam00001, 7tm_1, 7 transmembrane receptor (rhodopsin family)..」が見いだされた（７回膜貫通型receptor; Pfam00001）
- （戻る）
- 配列リストの右の「G」は「Entrez gene (遺伝子ごとに情報をとりまとめたデータベース)」へのリンク<br>
どのような情報がとりまとめられているか、確認してみましょう
- 結果上部のリンク「Reformat these Results」から結果を別の書式で表示させることができます。

- 【応用】「table format」は大量にサーチした結果の保存や結果のしぼりこみに便利。
    -結果をダウンロードして、エクセルで開いてみよう
    -結果上部のリンク「Edit and Resubmit」から生物種やキーワードでの検索結果のしぼりこみができます

>【実行が遅いときはここをクリック】[[あらかじめ検索した結果>http://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Get&VIEW_RESULTS=FromRes&RID=BEM4G44301N&UNIQ_OBJ_NAME=A_SearchResults_1KYsmC_415P_1Z57DM2et_23torn_1crIDF&QUERY_INDEX=0]]

- 【参考】: cDNAやESTのゲノムへのマッピング（貼り付け）は、BLATのほうがよい<br>
// のちほど「真核生物のスプライスサイト予測」で利用します。結果の見え方や速度を比較しましょう

//-系藤樹を表示させよう
//--下へスクロールして「Alignments」の上から順に数本にチェック入れる
//--「Distans tree of results」をクリック
//--「Tree Method」を「Fast Minimum Evolution」から「Neighbour joining」に変更したり、樹型を「rectangle」から「slanted」「radial」などに変更してみましょう

- 【応用】: 検索結果で得られた類似な配列をまとめどりしよう
    -統合TV本家: http://togotv.dbcls.jp/20070926.html
([[YouTube>http://www.youtube.com]]版: http://www.youtube.com/watch?v=RhTmgpOIUIw ) を参照

- 【応用】: PSI-BLASTを使うと、類似が低いが遠縁であるような配列を捕まえることもできます。上記の配列で実行してみましょう。
    -統合TV本家: http://togotv.dbcls.jp/20071016.html
([[YouTube>http://www.youtube.com]]版: http://www.youtube.com/watch?v=iIufC3uNlEk ) を参照

//-【応用】:「マトリクス」をかえて検索してみましょう。
//-e-valueとは？
//-E = Kmn^(e-λS)
//<br>そのライブラリで偶然に同じスコアでヒットする''本数''の期待値

        --
[[AJACS蝦夷/講習内容]]へもどる
