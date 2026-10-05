# 第2回 Webエンジニアリング演習 レポート

## 学籍番号
4724228

## コンフリクトが発生した理由
（2つのブランチと同じ行の変更を説明）
同じ出発点のmainから分岐したpractice/conflict-aとpractice/conflict-bにおいて、同じファイルの同じ行を編集しコミットしたので、
先にconflict-aの変更がmainに取り込まれたあと、conflict-bの側でmainの最新状態を取り込もうとしたから。
この時に、GitHabから見ると「すでに main に入っている変更のA」と「これから入れようとしている自分の変更のB」が、同じ場所で矛盾しているため、どちらを残せばいいか自動で判断できなかったから。

## 解決手順
（実行した操作を順に記載）
README.mdの競合している記号を削除して「- ブランチを使い、コンフリクトも自分で解決する」に変更する。
@4724228 ➜ /workspaces/web-eng-report (practice/conflict-b) $　git status
@4724228 ➜ /workspaces/web-eng-report (practice/conflict-b) $　git add README.md
@4724228 ➜ /workspaces/web-eng-report (practice/conflict-b) $　git commit -m "Resolve README conflict"
@4724228 ➜ /workspaces/web-eng-report (practice/conflict-b) $　git push
GitHubで競合が解消されたことを確認
プルリクエストを main へマージする。

## 履歴
（git log --oneline --graph --all の結果）
@4724228 ➜ /workspaces/web-eng-report (main) $ git log --oneline --graph --all
*   a1b636a (HEAD -> main, origin/main, origin/HEAD) Merge pull request #3 from 4724228/practice/conflict-b
|\  
| *   16d2a4e (origin/practice/conflict-b, practice/conflict-b) Resolve README conflict
| |\  
| |/  
|/|   
* |   74eb57b Merge pull request #2 from 4724228/practice/conflict-a
|\ \  
| * | 6810b23 (origin/practice/conflict-a, practice/conflict-a) Update goal in conflict A
|/ /  
| * 130794f Update goal in conflict B
|/  
*   f3abc2c Merge pull request #1 from 4724228/feature/add-readme
|\  
| * 5cf33ea (origin/feature/add-readme) Add README
|/  
* 9841a64 Add REPORT_01.md
* 30fbde2 Add index.html
* 140543a Add devcontainer configuration for Web Engineering
* 00f4420 Initial commit