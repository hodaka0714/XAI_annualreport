# 概要

修士論文「Explainable AIを用いた有価証券報告書の分析」で用いた**日経平均採用銘柄225社の決算データ**に関するレポジトリです。

225社の損益計算書の数値や経営状況に関する記述に関する情報が含まれております。


# 各ファイルについて

## sample_notebook.ipynb

CSVファイルの中身を簡単に確認したい方のために制作しました。まずはこちらをご覧ください。

## master_thesis.pdf

このデータを用いて行った研究内容です。興味がございましたら、ご覧ください。

## CSVファイル

合わせて7つのCSVファイルを公開しています。

### 0_id_name.csv
 
 1-6までのCSVのidと社名を紐付けたデータです。
 
 ![](https://github.com/hodaka0714/XAI_annualreport/blob/main/images_for_readme/0.png)
 
 
### 1_nikkei225_2015_2019.csv
 
 2019年度の有価証券報告書から抽出した2015年度-2019年度の損益計算書の数値データです。すべての会社で2015年度からのデータが揃っているわけではないので、合計1063行となっております。
 
  ![](https://github.com/hodaka0714/XAI_annualreport/blob/main/images_for_readme/1.png)
 
### 2_keiei_tfidf.csv
 
 経営に関する記述(5_description_2018.csv)から算出した、以下の2つの特徴量が入ったデータです。
 * 記述をTF-IDFしSVDで次元削減したベクトル (one-fiveは下の項目と一致しています)
 * 各社の5項目の記述文字数
 
 また「経営に関する項目」とは有価証券報告書に記載の以下の5項目です。
```
1. 経営方針，経営環境及び対処すべき課題等 (keiei)
2. 事業等のリスク (risk)
3. 経営者による財政状態，経営成績及びキャッシュ・フローの状況の分析 (money)
4. 経営上の重要な契約等 (contract)
5. 研究開発活動 (research)
```

  ![](https://github.com/hodaka0714/XAI_annualreport/blob/main/images_for_readme/2.png)
 
### 3_emotion_score.csv
 
 経営に関する記述(5_description_2018.csv)から算出した、各文章の印象分析が入ったデータです。5項目225社に対し、ネガティブ/ポジティブ/ニュートラルの3つの値を、Microsoft AzureのText Analytics APIを用いて取得しました。一度に投げられる文字数に制限があったことから、記述内容が5120文字を超える場合は、初めの5120文字を採用しました。
 
![](https://github.com/hodaka0714/XAI_annualreport/blob/main/images_for_readme/3.png)
 
### 4_description_2018.csv
 
2018年度有価証券報告書の経営に関する記述5項目をまとめたデータです。

  ![](https://github.com/hodaka0714/XAI_annualreport/blob/main/images_for_readme/4.png)
 
### 5_description_2019.csv
 
 2019年度有価証券報告書の経営に関する記述5項目をまとめたデータです。
 
   ![](https://github.com/hodaka0714/XAI_annualreport/blob/main/images_for_readme/5.png)
 
