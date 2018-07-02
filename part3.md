[[AJACS蝦夷/講習内容]]へもどる

        --
目次

#contents
        --
#  自己紹介 [#d139e45a]

## 講師の中尾 [#e8690c16]
- 30代半ば。かずさディー・エヌ・エー研究所 特別研究員

- こんな人です。
    - http://d.hatena.ne.jp/nakao_mitsuteru/
    - http://kdri.g.hatena.ne.jp/nakao_mitsuteru/
    - http://bioruby.g.hatena.ne.jp/nakao_mitsuteru/
    - http://twitter.com/32nm

- 北大理化II→京大→東大医科研→産総研CBRC→かずさDNA研　「ゲノムスケール」の「情報」を扱ってきました。

## 参加者アンケート [#y80508ff]
- バイオインフォマティクスを使っている人：13
- プログラミングをたしなむ人：3
- おもにMacの人：6
- おもにWindowsの人：18
- ウェブブラウザはFireFoxの人：9
- ウェブブラウザはSafariの人：3
- データベースを良く利用する人：15
- 統合データベースプロジェクトのウェブサイトを見たことがある人：
- データベースを構築している人：2
- データベースを構築したい人：5


# 塩基配列の注釈（annotation）の基礎 [#wc3e65b6]
##  ゲノムの注釈 genome annotation [#t2455a15]
- 構造注釈 structural annotation<br>
遺伝子の構造、リピート配列構造などを記載したアノテーション
- 機能注釈 functional annotation<br>
遺伝子の機能を記載したアノテーション

- http://www.ncbi.nlm.nih.gov/entrez/viewer.fcgi?db=nuccore&id=4732164 (F10A2 entry)
featuresなどの注釈がどのようについているのか、眺めてみましょう。

- International Nucleotide Sequence Database Collaboration http://www.insdc.org
    - JP: DDBJ http://www.ddbj.nig.ac.jp/
    - EU: EMBL http://www.ebi.ac.uk/embl/
    - USA: GenBank http://www.ncbi.nlm.nih.gov/Genbank/

- ゲノムデータベースの例
    -Cyanobacteria: http://www.kazusa.or.jp/cyanobase/ (photosynthesis)
        - [[Synechocystis sp. PCC6803 chromosome>http://bacteria.kazusa.or.jp/cyanobase/Synechocystis/map/Chr/cmap.html]]
        - [[slr1311 遺伝子>http://bacteria.kazusa.or.jp/cyanobase/Synechocystis/cgi-bin/orfinfo.cgi?title=Chr&name=slr1311&iden=1]]
    -Rhizobia: http://www.kazusa.or.jp/rhizobase/ (nitrogen-fixation)
    -Arabidopsis: http://www.arabidopsis.org/ (TAIR: flowering plant model)
        - [[CCA1 遺伝子座>http://www.arabidopsis.org/servlets/TairObject?id=137165&type=locus]]
        - [[CCA1 遺伝子モデル>http://www.arabidopsis.org/servlets/TairObject?id=138515&type=gene]]
    -Ensembl: http://www.ensembl.org/ (human, animals, disease-related)


## 遺伝子の「構造 structure」を予測すること [#qabdbe8f]
- DNAは読めるが、それだけでは遺伝子はわからない。
- ゲノムを読んだら遺伝子の構造を把握することがまず第一。

## 遺伝子構造アノテーションの基礎 [#j1b06abf]
## 類似配列検索 [#k5e0bd90]
//-既知の遺伝子に類似な配列は遺伝子たぶん
//-オーソログ ortholog （種分化と同時に遺伝子が分離）
//-パラログ paralog （種のなかで遺伝子が重複）
//
- NCBI BLAST
    -http://www.ncbi.nlm.nih.gov/BLAST/
- DDBJ BLAST
    -http://blast.ddbj.nig.ac.jp/top-j.html
    -日本語・clustalwへの連続技が可能
- BLAT
    -http://genome.ucsc.edu/cgi-bin/hgBlat
    -高度な一致を検索する。やたらと高速

- 遺伝子発見ツール
//
    - Genemark.hmm
        -http://exon.gatech.edu/genemark/
        -http://exon.gatech.edu/genemark/gmhmm2_prok.cgi (for prokaryotes)<br>
Prediction models have been pre-computed for a 265 completely sequenced prokaryotic genomes from the NCBI RefSeq? database.
//
    - Glimmer
        -http://www.cbcb.umd.edu/software/glimmer/
        -http://www.ncbi.nlm.nih.gov/genomes/MICROBES/glimmer_3.cgi (server)<br>
（long ORFs からマトリクスを作り、遺伝子発見（ここでかけるにはjobが大き過ぎるのでパス）
//
//
//
#  真核生物のゲノム注釈 [#n049da92]

##  原核生物よりも困難な理由 [#mdb5a11a]
- 遺伝子密度が低い
- 遺伝子構造が複雑
    -エクソン＝イントロン構造
    -エクソンはタンパク質を指定する情報が載っている「コード領域」
    -イントロンは転写後にスプライシングにより切り捨てられる「非コード領域」
    -イントロンが切り出されることをスプライシングという
    -イントロンが切り出される位置をスプライスサイトという
    -スプライスサイトをきちんとおさえないと、コード領域が「ズレ」てしまう

##  真核生物は「コード領域予測＋スプライスサイト予測の組み合わせ」 [#u4d431e3]

##  コード領域予測の方法 [#x48c2fcc]
- 配列類似＋遺伝子予測法（原核生物と同じ）
- expressed sequence tags (EST) を貼り付ける（mapping）方法
    -dbEST: http://www.ncbi.nlm.nih.gov/dbEST
    -転写されたRNAを逆転写したものがcDNA (complementary DNA)
    -cDNAの端だけを重複をゆるして大量に読んだものがEST
    -転写(transcription)されたRNAを網羅的に研究する→「transcriptome」である
- 大量に存在するESTや、アミノ酸配列を貼り付けることで遺伝子を探す
    -GT-AGルールに従うのがキモ

- おすすめmapping tools
    -BLAT: http://genome.ucsc.edu/cgi-bin/hgBlat
    -sim4: http://globin.cse.psu.edu/globin/html/docs/sim4.html
    -wise: http://www.ebi.ac.uk/Wise2/ <br>
(protein sequence to a genomic DNA sequence, allowing for introns and frameshifting errors)

//** スプライスサイトの予測 [#od88d668]
//-保存されている短い配列パターンをコンセンサスという
//-スプライスサイトのコンセンサスは GT-AG しかない
//-スプライスサイトの周辺の微弱な情報を「総合」
//--ニューラルネットワークによるモデル化<br>
//モデル化に際しては、学習データの厳選が重要！
//-NetGene2 <br>
//http://www.cbs.dtu.dk/services/NetGene2/
//
##  真核生物ゲノムの遺伝子発見の実際 [#h7e503bf]
- 複数の解析方法の組み合わせによる画像化
- 手作業による「編集」が必須である
- それでも最大65%の精度<br>
実験の情報のフィードバックにより修正が必要


# ゲノムブラウザとアノテーション [#t890b7f6]
- ゲノム配列は分子生物学の白地図、なんでも載せることができる
- ゲノムブラウザは分子データのブラウザ
    - EST, cDNA, clone, contig, SNPs
    - 遺伝子モデル、シンテニー、リピート

- [[gbrowse>http://gmod.org/wiki/Gbrowse]]
    - [[Synechocystis>http://g.kazusa.or.jp/cgi-bin/gbrowse/Synechocystis/]]
    - [[Synechocystis sll0252の拡大>http://g.kazusa.or.jp/cgi-bin/gbrowse/Synechocystis/?start=1509265;stop=1509464;ref=Chr;width=1440;version=100;label=Chromosome%3Aoverview-dnaA%3Aoverview-tRNA%3Aoverview-Landmarks%3Aregion-BAC-Locus-ProteinCoding-CDS-Pseudogene-ncRNAs-cDNA-EST-tDNAs-Polymorphism-DNA-IPR-Web-PMID-Karyotype-plugin%3ARestriction%20Sites;id=0e6814b2709e9315ae1a81ea165e8d43;grid=on]]


- [[Ensembl>http://www.ensembl.org/index.html]]
    - [[Human (Homo sapiens) >http://www.ensembl.org/Homo_sapiens/index.html]]
    - [[21番染色体>http://www.ensembl.org/Homo_sapiens/mapview?chr=21]]
    - [[Contig>http://www.ensembl.org/Homo_sapiens/contigview?seq_region_right=46944323&seq_region_name=21&click_right=490&click_left=40&seq_region_left=1&seq_region_width=100000&vclick.x=112&vclick.y=335]]
    - [[Gene>http://www.ensembl.org/Homo_sapiens/geneview?gene=ENSG00000186975;db=core]]
    - [[Transcript>http://www.ensembl.org/Homo_sapiens/transview?transcript=ENST00000390690;db=core]]
    - [[Protein>http://www.ensembl.org/Homo_sapiens/protview?peptide=ENSP00000375109;db=core]]


## データとビュー [#m21542b5]
- データとデータベース
- データベース ← データ＋検索などの問い合わせ＋ビュー

## アノテーションの拡大解釈 [#h1ad8f81]
- 外部データベースリンク
    - SwissProt, [[UniProt>http://www.uniprot.org/]] タンパク質知識ベース
        - エントリ例：[[CCA1_YEAST>http://www.uniprot.org/uniprot/P21269]]
    - PDB、[[PDBj>http://www.pdbj.org/index_j.html]] タンパク質立体構造
        - エントリ例：[[1A3S>http://pdbjs3.protein.osaka-u.ac.jp/xPSSS/DetailServlet?PDBID=1A3S&PAGEID=Summary]]
    - [[KEGG>http://www.genome.jp/kegg/]] 代謝マップ
        - [[TCA Cycle>http://www.genome.jp/kegg/pathway/map/map00020.html]]
    - [[PubMed>http://pubmed.gov]] 文献
    - [[NCBI Gene>http://www.ncbi.nlm.nih.gov/sites/entrez?db=gene]], [[RefSeq>http://www.ncbi.nlm.nih.gov/RefSeq/]] 参照配列
    - [[NCBI GEO>http://www.ncbi.nlm.nih.gov/geo/]] 遺伝子発現

-  Ensembl
    - [[ContigView>http://www.ensembl.org/Homo_sapiens/contigview?seq_region_right=46944323&seq_region_name=21&click_right=490&click_left=40&seq_region_left=1&seq_region_width=100000&vclick.x=133&vclick.y=313]]
        - Overview
        - Detailed view
        - Basepair view
    - [[GeneView>http://www.ensembl.org/Homo_sapiens/geneview?gene=ENSG00000186975;db=core]]
    - [[TransView>http://www.ensembl.org/Homo_sapiens/transview?transcript=ENST00000390690;db=core]]
    - [[ExonView>http://www.ensembl.org/Homo_sapiens/exonview?db=core;transcript=ENST00000324988]]
    - [[ProtView>http://www.ensembl.org/Homo_sapiens/protview?peptide=ENSP00000375109;db=core]]


- View にほかのデータを追加する、合わせる。
- データだけを提供、流通、交換するしくみ。例：[[DAS: Distributed Annotation System>http://biodas.org]]
    - [[ProtView>http://www.ensembl.org/Homo_sapiens/protview?peptide=ENSP00000342827]]に外部データをあわせる。


## 【実習】ゲノムブラウザの利用、アノテーションの閲覧 [#c41e9a7f]

- Ensembl [[Human (Homo sapiens) >http://www.ensembl.org/Homo_sapiens/index.html]]
    - キーワード検索する（例：[[timeless>http://www.ensembl.org/Homo_sapiens/searchview?species=Homo_sapiens;idx=;q=timeless]])
    - 染色体からブラウズする（例：[[21番染色体>http://www.ensembl.org/Homo_sapiens/mapview?chr=21]]）

- [[GeneView>http://www.ensembl.org/Homo_sapiens/geneview?gene=ENSG00000163399;db=core]]、[[TransView>http://www.ensembl.org/Homo_sapiens/transview?transcript=ENST00000339159;db=core]]、[[ProtView>http://www.ensembl.org/Homo_sapiens/protview?peptide=ENSP00000342827]] にそれぞれどのようなデータやアノテーションがあるか確認する。違いは何か？

- [[ProtView>http://www.ensembl.org/Homo_sapiens/protview?db=core;peptide=ENSP00000295963]] の DAS Sources のチェックボックスをすべて入れて、update してみる。どこが変更されたか、どのようなアノテーションが追加されたか確認する。


        --
[[AJACS蝦夷/講習内容]]へもどる
