

# mirameet_Git
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**目次**

- 【Chapter1】VisualStudioCodeでGit操作
- 【Chapter2】コンフリクトの対処法について

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


***
# 【Chapter1】VisualStudioCodeでGit操作 
## ⑴Forkする

今回のmirameetのサイトを開き右上の"Fork"をクリック
![スクリーンショット 2021-07-15 091201](https://user-images.githubusercontent.com/66664167/125708745-3d79faf0-5995-45b2-a249-8be0a5a747cf.png)


クリックした後に自分の名前が記載されていれば完了
![スクリーンショット 2021-07-15 091724](https://user-images.githubusercontent.com/66664167/125709060-a6daa2e1-f9ad-4f94-9c7d-ddad96fb412f.png)



## ⑵ブランチを作成する
任意のブランチ名（今回はfeature1)を入力して"Create branch: feature1 from 'main'"をクリックする
```
feature1
```


![スクリーンショット 2021-07-15 102131](https://user-images.githubusercontent.com/66664167/125713381-cdfb2d6a-1687-431e-82a3-459dd0775393.png)



ブランチがfeature1になっていることを確認してindex.htmlの中身を書き換える
![スクリーンショット 2021-07-15 102155](https://user-images.githubusercontent.com/66664167/125713407-72b88151-79be-4522-bc7e-2d1e2371ba52.png)


Visualstudiocodeを起動し、OpenFolderをクリック


![スクリーンショット 2021-07-12 173603](https://user-images.githubusercontent.com/60914189/125257010-f3ec7b00-e337-11eb-9884-0818a82ee859.png)

## ⑶クローンする
### 1.<>CodeタブのCodeからURLをコピーする。
![スクリーンショット 2021-07-13 135828](https://user-images.githubusercontent.com/60914189/125394037-f73d4080-e3e3-11eb-9292-67ba978ae302.png)


今回はC:\User\ユーザーネームにクローンします。
<br>他の場所にクローンしたい方は”cd 任意のパス”で移動してからクローンしてください。



```
$ git clone コピーしたURL
```
![image](https://user-images.githubusercontent.com/60914189/125255343-488ef680-e336-11eb-8b05-8878a72219a4.png)
下記のような結果が返ってきたらクローンされています。
![image](https://user-images.githubusercontent.com/60914189/125255384-517fc800-e336-11eb-9c35-79ac33a27a54.png)


## ⑷クローンしてきたプロジェクトをVscodeで開く
先ほどクローンした場所まで移動

“mirameet_Git”をクリックし、”フォルダー”に反映されたことを確認したら”フォルダーの選択”をクリック
![スクリーンショット 2021-07-12 174254](https://user-images.githubusercontent.com/60914189/125257696-a1f82500-e338-11eb-8aaf-3a61f80c3297.png)

## ⑸Gitの基本設定をする
TerminalタブからNewterminalをクリックし、VScodeのターミナルに下記コマンドを入力する。
```
git config --local user.name ユーザー名
git config --local user.email メールアドレス
git config --local core.editor 'code --wait'
git config --local merge.tool 'code --wait "$MERGED"' 
git config --local push.default simple
```


![スクリーンショット 2021-07-15 094854](https://user-images.githubusercontent.com/66664167/125710925-d813aed8-fa8b-4319-add0-3354c224d37c.png)


下記コマンドで設定されているか一覧確認しましょう
```
git config --list
```

## ⑹ブランチを切り替える
cloneしてきたファイルを開いたら左下のブランチを確認する。
<br>main(master)ならクリックし、先ほどGitHubで作成したfeature1をクリックする。
![スクリーンショット 2021-07-15 180441](https://user-images.githubusercontent.com/66664167/125761772-bf48b162-4c44-47ce-b7fe-fb0d80e1d93d.png)




feature1に切り替わったことを確認する。
![スクリーンショット 2021-07-15 180503](https://user-images.githubusercontent.com/66664167/125761806-1ac594e9-ff39-4ff0-baa0-7050d9af382c.png)



## ⑺目標物の確認
今回はカンタンにhtmlファイルの文言を書き換えてみましょう。
<br>左が修正前の表示で、今回修正すると右のような表示になります。
![スクリーンショット 2021-07-15 160228](https://user-images.githubusercontent.com/66664167/125744081-c0c6fe46-006d-4b8d-ba4c-20cb54935579.png)



## ⑻文言を書き換える
index.htmlを開き14行目の「【Git入門】　Gitの使い方を理解しよう」を
<br>下記の文言に書き変える
```
【Git入門】 文言を書き換えてみよう
```
![スクリーンショット 2021-07-15 100227](https://user-images.githubusercontent.com/66664167/125711719-beb57f19-9efa-4f3b-b41e-9028e3252856.png)


## ⑼変更を保存する
書き変えたらCtrl+Sで保存する。未保存の場合は変更したファイル名に”●”がつく
![スクリーンショット 2021-07-13 142148](https://user-images.githubusercontent.com/60914189/125395105-b0e8e100-e3e5-11eb-996b-e0433bea0542.png)


## ⑽ステージングを行う
### 1.VSCodeでステージング
VSCodeでステージングを行うので左側のソース管理アイコンをクリックしてGitメニューを開く
![スクリーンショット 2021-07-13 142237](https://user-images.githubusercontent.com/60914189/125395171-cb22bf00-e3e5-11eb-8b67-ce3abfeb558d.png)

### 2.ソース管理アイコンを押したら、ファイル右にある「＋」をクリックする
![スクリーンショット 2021-07-13 142333](https://user-images.githubusercontent.com/60914189/125395275-ed1c4180-e3e5-11eb-8f1f-25ab58f0a164.png)

### 3.Staged Changesに書き換えたファイルが入る。ここで変更点を確認出来る。
![スクリーンショット 2021-07-13 142427](https://user-images.githubusercontent.com/60914189/125395365-10df8780-e3e6-11eb-9cf8-4b6833614ebc.png)



## ⑾コミットを行う
Messageに下記コメントを記入し、メニュー上部にある“✓”アイコンを押す。
<br>“✓”はコミットアイコン
```
#1 タイトルの変更
```
![スクリーンショット 2021-07-15 105922](https://user-images.githubusercontent.com/66664167/125716402-2958852c-74a2-418f-a8f3-24bc5ea6e08b.png)

## ⑿feature1ブランチにプッシュ
ソース管理をクリックし、三点リーダーのプッシュでプッシュする
![スクリーンショット 2021-07-15 154842](https://user-images.githubusercontent.com/66664167/125742650-126c4ffe-25ad-48fe-b967-a21e9630a7f4.png)


## ⒀変更内容がGitHubに反映されたかの確認をする
index.htmlの中身と最終更新日時を確認する。反映されていない場合はF5キーで更新し再度確認する。

![1dsdsする](https://user-images.githubusercontent.com/66664167/125724030-8a35bf9c-0bd8-4436-b1f5-3b7147a976ae.png)



画面上部に”feature1 had recent pushes 1 minute ago”のようなメッセージが表示されるのでCompare&pull requestをクリック

## ⒁プルリクエストを作成する
![スクリーンショット 2021-07-15 122556](https://user-images.githubusercontent.com/66664167/125724574-40dd703f-74e4-49c1-862f-d8fbf97d7d87.png)


## ⒂変更内容の確認
変更内容の確認を見てみましょう。

![スクリーンショット 2021-07-15 123007](https://user-images.githubusercontent.com/66664167/125724802-06821f2c-4989-4349-8d15-527088607392.png)


## ⒃ソースコードの確認
「Pull requests」タブを開き、「Files changed」からソースコードを確認する。
![スクリーンショット 2021-07-15 123242](https://user-images.githubusercontent.com/66664167/125725036-3f3baa85-4639-42c1-b053-de665cbcc1cf.png)


## ⒄マージする
内容に問題がなければ、「Conversation」の「Merge pull request」をクリックしてレビューを完了する。
![17](https://user-images.githubusercontent.com/66664167/125744791-ebe9b553-f2d4-4b72-a8b4-8bf91792ff65.png)


## ⒅マージ後ブランチ削除
プルリクエストが成功したら"Delete branch"をクリックしてブランチを削除
![デリートブランチ](https://user-images.githubusercontent.com/66664167/125726049-1876d572-1216-4ef6-850c-396b73a76611.png)

## ⒆マージ後確認
自分のmainブランチに反映してるか、確認してみましょう。
![18以降プルリクエスト後からマージ](https://user-images.githubusercontent.com/66664167/125726252-9afb0500-128a-49ed-91ee-62f7298861bf.png)
![マージ後確認スクショ](https://user-images.githubusercontent.com/66664167/125726268-869cbcd0-f4dd-4e29-92b1-4d58b2e2da81.png)




# 【Chapter2】コンフリクトの対処法

## ⑴新規でブランチを作成
### 1.  VisualStudioCodeのブランチが表示されているところをクリックし、ブランチ作成
![スクリーンショット 2021-07-12 153032](https://user-images.githubusercontent.com/60914189/125241195-1ecdd380-e326-11eb-8cb0-1b67b4ce66ac.png)


ブランチ名は下記を入力
```
feature2
```
### 2. ブランチ名がfeature2になったのを確認しましたら再度index.htmlに修正を加えます。
![スクリーンショット 2021-07-15 103816](https://user-images.githubusercontent.com/66664167/125715096-977e4495-805a-4416-baa8-50621df4e290.png)

## ⑵index.htmlを修正
### 1.ブランチ名がfeature2になっているのを確認。再度index.htmlに修正を加えます。

### 2.以下のソースをindex.htmlの31行目以降に挿入します。
挿入後上書き保存を行いローカルの修正を確認しましょう。
```
【Git入門】 コンフリクトを理解しよう
```
![スクリーンショット 2021-07-12 154425](https://user-images.githubusercontent.com/60914189/125242781-170f2e80-e328-11eb-9715-54c4ad45b955.png)

## ⑶コンフリクトを起こしてみる
### 1.ここでコンフリクトを発生させるためにindex.htmlをGitHub上で直接編集したいと思います。
<br>GitHubを開き、index.htmlをクリックして下さい。

![1](https://user-images.githubusercontent.com/66664167/125714066-80fb1097-b358-496d-913f-d71e0f1d707f.png)

### 2.index.htmlが表示されましたら右上のペンのマークの”Edit this file”をクリックし編集できるようにします。
![2](https://user-images.githubusercontent.com/66664167/125714073-5f801a84-91f6-4392-8f8e-2c6ac2212168.png)


### 3.先ほどと同じ32行目に以下の文言を追加します。
```
【Git入門】 コンフリクトは注意が必要です。
```
![3](https://user-images.githubusercontent.com/66664167/125714084-e1df225d-a144-4156-b85c-f030710f6f8c.png)


### 4.Commit changesをクリックし修正をコミットします。
![image](https://user-images.githubusercontent.com/60914189/125245636-c568a300-e32b-11eb-9fa2-2d500df566d1.png)

### 5.Commit changesをクリックし修正をコミットします。


![5](https://user-images.githubusercontent.com/66664167/125714102-8ee79f2d-b526-4765-b010-4b92d2de3c73.png)
<br>これでmasterブランチのソースには32行目に文言が入った状態になりました。

### 6.Vscodeに戻り、先ほどの修正をPushしてみましょう。

ソースを保存した状態で左側メニューの＋マークをクリックし
修正をステージにあげます。
![スクリーンショット 2021-07-12 161928](https://user-images.githubusercontent.com/60914189/125246769-2e9ce600-e32d-11eb-9ebd-86639f825240.png)

### 7.ステージにあげた修正をコミットします。 

✓マークをクリックし下記のメッセージを入力しEnterキーを押します。
```
#2 文書の追加
```
![2-7](https://user-images.githubusercontent.com/66664167/125874220-68004466-0f5e-4cd1-8bfc-112edb438d94.png)


### 8.Pushを行う
…マークを押しメニューを出しその中のプッシュを選択します。
<br>ブランチの公開が確認されるのでOKボタンをクリックします。
![image](https://user-images.githubusercontent.com/60914189/125247038-79b6f900-e32d-11eb-8a8e-0664920d3797.png)


![image](https://user-images.githubusercontent.com/60914189/125247055-7cb1e980-e32d-11eb-9c81-fba1fad454f5.png)


## ⑷コンフリクトの対処について
### 1.GitHubに戻りプルリクエストを作成していきます。
Compare & pull requestキーをクリックします。
![4-1](https://user-images.githubusercontent.com/66664167/125715547-71ea5517-50d7-4a04-99fc-46c311f98359.png)


### 2.Create pull requestキーをクリックします。
![4-2](https://user-images.githubusercontent.com/66664167/125715556-17338f0e-3480-4c0f-bfb5-4924690af649.png)

### 3.コンフリクト解消
Pullリクエストが作成されましたが先ほどと違いコンフリクトが発生しております。
<br>このままでは修正を反映できませんので、コンフリクトの解消を行いましょう。
![スクリーンショット 2021-07-12 162831](https://user-images.githubusercontent.com/60914189/125247749-3d37cd00-e32e-11eb-9556-1628a0fc5c09.png)
赤枠部分で上がfeature2、下がmasterでの状態を表示しています。
<br>今回はfeature2の内容で反映していきたいと思いますので33行目だけを残すように修正します。

![スクリーンショット 2021-07-12 162934](https://user-images.githubusercontent.com/60914189/125247903-68222100-e32e-11eb-9c02-b843e598ccb7.png)

修正後にMark as resolvedをクリックし修正を反映します。
コミットが出来るようになりますので
Commmit mergeでコミットします。



![125247933-6f492f00-e32e-11eb-9952-f55652bbdff7 (2)](https://user-images.githubusercontent.com/66664167/125715723-2ce07160-10a8-484a-8008-c1e9c6694ea3.png)



コンフリクトが解消したので、再度プルリクエストを作成します。
<br>Merge pullrequestをクリックします。

![image](https://user-images.githubusercontent.com/60914189/125247966-7a03c400-e32e-11eb-8259-82a53471aef9.png)


下記のメッセージを入力し、"Confirm merge"をクリックしてください
```
文書を追加
コンフリクトを解消
```


![コンフリクト　デリートブランチ](https://user-images.githubusercontent.com/66664167/126097989-c8dcb261-e8d3-44fc-bacc-ceeef141df8b.png)





プルリクエストが正常に作成できました
<br>最後にChapter1同様にブランチを削除しましょう。

