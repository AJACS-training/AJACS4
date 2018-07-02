[[AJACS蝦夷/講習内容]]へもどる

        --
目次

#contents
        --

# 遺伝子機能予測とDB高度化 [#a53f2e4d]

## 遺伝子の機能をしるためには [#w125ab8c]
機能が「本当の意味で」判明している遺伝子はおどろくほどすくない

## 実験で知る・推し量る [#bb812166]
- 酵素活性をはかる
    -遺伝子（DNA）→転写→RNA→翻訳→タンパク質
    -タンパク質をとり、どんな酵素活性をもつか調べる
- 逆遺伝学
    -古典的遺伝学　形態や現象から遺伝子へ
    -逆遺伝学　遺伝子から形質や現象へ＝遺伝子を「潰す」
- 転写差物の動態を観察する

## 類推する方法は？ [#i5eb422d]
- 配列の類似
    -配列が似ていれば機能も似ている（多分）
    -類似の類似の類似の類似は類似でないかもしれない
        -「相同」（homology）人の手＝猫の手＝鳥の羽
        -「相似」（similarity）コウモリと鳥の羽、パンダの親指
    -部分一致している部分は機能と関わらないかもしれない
    -機能とかかわれない領域の部分的な一致が非常に危険

//-嘘類似の問題回避法
//
- 配列類似検索の対象は、信頼できる配列セットから順に使う
    -UniProtKB/SwissProt: http://www.ebi.ac.uk/swissprot/
    -UniProtKB/TrEMBL: http://www.ebi.ac.uk/trembl/
    -NCBI nr: http://www.ncbi.nlm.nih.gov/Education/blasttutorial.html (description)
- 配列類似検索以外の機能予測方法を用いる<br>
機能に関わるタンパク質の部分配列
    -機能に関わるタンパク質の部分配列（モチーフやドメイン）
    -Interpro: さまざまなタンパク質機能探索のための統合データベース<br>
http://www.ebi.ac.uk/interpro
- 注釈の「根拠 (evidence)」が明示できる方法で注釈する<br>
機能アノテーションの「根拠」を記載する方法が提唱されている
    -see: http://www.geneontology.org/ -> Documentation -> Evidence Code Guide
        -IDA (Inferred from Direct Assay)
        -TAS (traceable author statement)
        -IEA (Inferred from Electronic Annotation)
        -ISS (Inferred from Sequence or Structural similarity) etc.



# 【実習】Interpro・GO・[[KazusaAnnotation>http://a.kazusa.or.jp]] [#n1949186]

## Interproscan [#pae0a7cf]

&color(green){モチーフ、プロファイル検索のまとめがけ、Gene Ontrogyにまで到達可能な優れたアミノ酸配列解析総合サイト};

+googleの検索窓に「interproscan」と入れて、googleで探し出す ( http://www.ebi.ac.uk/InterProScan/ )
- Enter or Paste a PROTEIN Sequence in any formatに以下の配列をコピペする (ctl-C then ctl-V)
 >opsin Rh2(Drosophila melanogaster)
 MERSHLPETPFDLAHSGPRFQAQSSGNGSVLDNVLPDMAHLVNPYWSRFAPMDPMMSKIL
 GLFTLAIMIISCCGNGVVVYIFGGTKSLRTPANLLVLNLAFSDFCMMASQSPVMIINFYY
 ETWVLGPLWCDIYAGCGSLFGCVSIWSMCMIAFDRYNVIVKGINGTPMTIKTSIMKILFI
 WMMAVFWTVMPLIGWSAYVPEGNLTACSIDYMTRMWNPRSYLITYSLFVYYTPLFLICYS
 YWFIIAAVAAHEKAMREQAKKMNVKSLRSSEDCDKSAEGKLAKVALTTISLWFMAWTPYL
 VICYFGLFKIDGLTPLTTIWGATFAKTSAVYNPIVYGISHPKYRIVLKEKCPMCVFGNTD
 EPKPDAPASDTETTSEADSKA
+Submit Job をクリックしてジョブをスタート
+グラフィクス表示とTable表示の両方でこの配列がもつモチーフ・プロファイルを確認

- 【発展】どのようなプログラムが使われているのか？それぞれの詳細について調査し理解しましょう


## GO: Gene Ontology [#ga9671d6]

&color(green){遺伝子機能注釈のための生物共通語彙を提供。evidence が明記されているのはすばらしい};

- http://www.geneontology.org
++transcription repressor activityで検索
++数が多すぎるので、フィルターの「Data source」を「TAIR」に「Evidence code」を「IDA」にして[Set filters]
++CCA1, CIRCADIAN CLOCK ASSOCIATED 1 をクリックして遺伝子の詳細を見る 【evidence codeに注意】
++ フィルターの「Evidence code」を「All」にして[Set filters]　【それぞれのevidence codeに着目】
++circadian rhythm (GO:0007623) をクリックしてGOの詳細を見る
++Term Lineageのcircadian rhythmの数字の部分をクリックして、タームに関連する遺伝子のリストを表示する【ここでも、それぞれのevidence codeに着目】
++Evidence CodeをIDA (Inferrd from Direct Assay) に限定するfilterをかけてみる。speciesをA. thalianaに限定してみるなどの操作を行ってみる。IDA, TASなど、複数のEvidence codeを反転させたいときは、Macならcommand key+クリック, windowsの場合はCtrl+クリック。


## [[KazusaAnnotation:http://a.kazusa.or.jp]] [#t1c75a37]

&color(green){統合DBプロジェクトにおける、オープンアノテーションへの挑戦。現在進行形};

- 遺伝子アノテーションの実施、共有、公開の場を提供
    -ウェブアノテーション／ソーシャルブックマーク／URLにアノテーションできるツール
    -ゲノムデータベースが遺伝子のURLを提供
    -アノテーション ＝ 遺伝子（URL）、ユーザ、コメント、タグ、タイムスタンプ
    -[[タグ>http://a.kazusa.or.jp/tags]]でゆるやかにアノテーションを分類
    -登録ユーザは自由にアノテーションを追加できる。
        - ユーザ登録は、http://openid.dbcls.jp でアカウントを取得してから http://navi.kazusa.or.jp でできます。【宿題】

- http://a.kazusa.or.jp/
    - キーワード検索（例：[[photosystem>http://a.kazusa.or.jp/annotation?q=photosystem]]）
    - [[76 annotations>http://a.kazusa.or.jp/annotation/show?uri=http%3A%2F%2Fbacteria.kazusa.or.jp%2Fcyanobase%2FSynechocystis%2Fcgi-bin%2Forfinfo.cgi%3Ftitle%3DChr%26name%3Dsll1091%26iden%3D1]] というようなところをクリックして、アノテーション先のページのページを開く。
        - [[タグ pmid:15694347>http://a.kazusa.or.jp/tags/show?name=pmid%3A15694347]] をクリックして内容を確認する。<br>pmid:15694347という論文からつけられたアノテーションが（この遺伝子を含む）リストが表示される。
        - [[タグ CyanoGenes:463>http://a.kazusa.or.jp/tags/show?name=CyanoGenes%3A1677]] をクリックして内容を確認する。<br>CyanoGenesとして登録されたレコードが表示される。

- Gene Indexing
    - KazusaAnnotation を利用した持続的な遺伝子アノテーションの実証実験
    - 文献中に出現する遺伝子名の場所を記録
        - [[Title>http://a.kazusa.or.jp/tags/show?name=title]], Abstract, Results, Table 1, Figure 1, ...
        - ファクトデータ、廃れない、
        - 専門知識が少なくても追加作業ができる
        - 遺伝子側からのビュー [[例：slr1311>http://a.kazusa.or.jp/annotation/show?uri=http%3A%2F%2Fbacteria.kazusa.or.jp%2Fcyanobase%2FSynechocystis%2Fcgi-bin%2Forfinfo.cgi%3Ftitle%3DChr%26name%3Dslr1311%26iden%3D1]]
        - 文献側からのビュー [[例：PMID:12228353>http://a.kazusa.or.jp/tags/show?name=pmid%3A12228353]]


### CyanoGenes [#mbef529d]

&color(green){シアノバクテリアの遺伝子単位のコメント受付。オープンアノテーションの最初期の試み};
- http://www.kazusa.or.jp/cyanobase/Synechocystis/comments/ 旧サイト
- http://a.kazusa.or.jp/tags/show?name=CyanoGenes 移行中



//**ExPASy [#vfb081e5]
//&color(green){proteomics に関係したオリジナルツール＆他サイトへのリンクが豊富};
//-http://www.expasy.org/ <br>
//The ExPASy (Expert Protein Analysis System) proteomics server of the Swiss Institute of Bioinformatics (SIB) is dedicated to the analysis of protein sequences and structures as well as 2-D PAGE <br>
//--タンパク質の同定 (peptide mass fingerprint, pI, MW etc.): Aldente, TagIdent, MultiIdent, AACompIdent
//--翻訳後修飾や切断部位の推定: Findmod, FindPept, GlycoMod <br>
//などなど、多数のツールを提供。


# 【実習】DB高度化 [#x878e13f]
統合データベースセンターのサービスをつかってみましょう。
共有、公開、利用がコンセプト。

## 生命科学データベース横断検索 [#x2e7d36f]
- http://lifesciencedb.jp/dbsearch/

## OReFiL オンラインリソースファインダー [#f1dff656]
- http://orefil.dbcls.jp/

## Alle 略語の正式名称を検索 [#s09786b0]
- http://allie.dbcls.jp/

## 生物アイコン [#l6246cd2]
- http://lifesciencedb.jp/lsdb.cgi?gg=resource_icon
- [[一括ダウンロード>http://lifesciencedb.jp/MEXT_H18/ii-7d71540862808853958b767a30fb63d04f9b/ii-1-8f9e66f830b730bd30fc30e930b9/ii-1-8f9e66f830b730bd30fc30e930b9]]
- [[表示 2.1 日本（CC-BY 2.1 JP）クリエイティブコモンズ>http://creativecommons.org/international/jp/]]のライセンスで公開。
    -http://creativecommons.org/licenses/by/2.1/jp/
    -利用には原著作者のクレジットを表示しなければならない。
    -複製、頒布、展示、実演することができます。
    -二次的著作物を作成することができます。


## アナトモグラフィー 解剖学整理棚 [#a0fdc7d0]
- http://lifesciencedb.jp/ag/

## 統合ウェブサービス - togows.dbcls.jp [#hd5f8516]
- http://togows.dbcls.jp/
- NCBI, DDBJ, KEGG, PDBj の共通API を SOAP と [[REST>http://togows.dbcls.jp/site/rest.html]] で提供
- [[REST API>http://togows.dbcls.jp/site/rest.html]]
    -NCBI GenBank
        - http://togows.dbcls.jp/entry/genbank/HUMIGHAF
        - http://togows.dbcls.jp/entry/genbank/HUMIGHAF.xml
        - http://togows.dbcls.jp/entry/genbank/HUMIGHAF.fasta
        - http://togows.dbcls.jp/entry/genbank/HUMIGHAF/definition
        - http://togows.dbcls.jp/entry/genbank/HUMIGHAF/seq
        - http://togows.dbcls.jp/entry/genbank/HUMIGHAF/seq
    -NCBI PubMed
        -http://togows.dbcls.jp/entry/pubmed/16381885
        -http://togows.dbcls.jp/entry/pubmed/16381885.xml
        -http://togows.dbcls.jp/entry/pubmed/16381885/abstract
        -http://togows.dbcls.jp/entry/pubmed/16381885/au
        -http://togows.dbcls.jp/entry/pubmed/16381885/authors
        -http://togows.dbcls.jp/entry/pubmed/16381885/so
        -http://togows.dbcls.jp/entry/pubmed/16381885/mesh
        -文献のタイトルや著者名の取り出しに[[KazusaAnnotationで利用しています>http://a.kazusa.or.jp/tags/show?name=pmid%3A15029958]]
    -PDBj
        -http://togows.dbcls.jp/entry/pdb/1a4u
        -http://togows.dbcls.jp/entry/pdb/1a4u/accession
        -http://togows.dbcls.jp/entry/pdb/1a4u/keywords
        -http://togows.dbcls.jp/entry/pdb/1a4u/chains
        -http://togows.dbcls.jp/entry/pdb/1a4u/models
    -KEGG COMPOUND
        -http://togows.dbcls.jp/entry/compound/C00001
        -http://togows.dbcls.jp/entry/compound/C00001/entry_id
        -http://togows.dbcls.jp/entry/compound/C00001/name
        -http://togows.dbcls.jp/entry/compound/C00001/names
        -http://togows.dbcls.jp/entry/compound/C00001/formula
        -http://togows.dbcls.jp/entry/compound/C00001/mass
        -http://togows.dbcls.jp/entry/compound/C00001/remark
        -http://togows.dbcls.jp/entry/compound/C00001/glycans
        -http://togows.dbcls.jp/entry/compound/C00001/reactions
        -http://togows.dbcls.jp/entry/compound/C00001/rpairs
        -http://togows.dbcls.jp/entry/compound/C00001/enzymes
        -http://togows.dbcls.jp/entry/compound/C00001/kcf
        -http://togows.dbcls.jp/entry/compound/C00001/comment


## TogoDB 誰でもデータベース構築 - togodb.dbcls.jp [#uaee1ab0]
- http://togodb.dbcls.jp/
- 表形式のデータをアップロード　簡単にウェブで公開／共有

        --
[[AJACS蝦夷/講習内容]]へもどる
