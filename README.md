## Githubの使い方の練習

```
git clone https://github.com/ayurrin/git-practice.git
git checkout develop

```
ブランチを作成
```
git checkout -b ブランチ名
```
git-practiceフォルダにhtmlファイルを作成して1行目に適当に何か書いて保存

```
git add .
git commit -m "メッセージ"
git push -u origin ブランチ名
```
https://github.com/ayurrin/git-practice.git
ここにアクセスしてcreate pull request
developにブランチをマージする

変更をローカルに反映developに移動
```
git pull
git checkout develop
```


二人組になって相手のhtmlファイルを編集して
```
git add .
git commit -m "メッセージ"
git push -u origin develop
```

```
 ! [rejected]        develop -> develop (fetch first)
error: failed to push some refs to 'https://github.com/ayurrin/git-practice.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

```
このようになった人は
```
git pull
```
してもう一度pushを実行

再び自分のブランチに戻る
```
git checkout ブランチ名
```
でもう一度最初に作ったブランチに移動して、最初に自分が作ったファイルを編集保存。

```
git add .
git commit -m "メッセージ"
git push -u origin ブランチ名
```
コンフリクトが起きているのでcreate pull requestした後、resolve conflictで相手が編集した部分の下に自分がさっき編集した部分が来るようにする（>>みたいなのは削除）

コンフリクトの解消方法の参考になる
https://qiita.com/hkengo/items/f47b9f50ac2dca407d12

### 親ブランチにmergeする方法
```
git checkout develop
git merge ブランチ名
```

### git add の取り消し
```
git reset HEAD <filename>
```
<filename>を入力しなければすべてのファイル

### ローカルでごちゃごちゃしたけど元に戻したいとき
```
git checkout <filename>
```
<filename>を入力しなければすべてのファイル