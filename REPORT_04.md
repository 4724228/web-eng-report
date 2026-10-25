# 第4回 Webエンジニアリング演習 レポート
## 学籍番号
4724228


## `const`と`let`の宣言・再代入に使用したコード
const courseName = "Web Engineering";
let retryCount = 1;

courseName = "Other Course"; 
retryCount = 2;


## VSCodeと`pnpm run check`に表示されたエラー番号・メッセージ

エラー番号：TS2588

$ tsc --noEmit src/index.ts
src/index.ts:26:1 - error TS2588: Cannot assign to 'courseName' because it is a constant.
26 courseName = "Other Course";
   ~~~~~~~~~~
Found 1 error in src/index.ts:26
[ELIFECYCLE] Command failed with exit code 2.


## 修正後の実行結果と`const`・`let`の違いの説明

(修正後の実行結果)
@4724228 ➜ /workspaces/-web-eng-typescript (main) $ pnpm run check
$ tsc --noEmit src/index.ts
@4724228 ➜ /workspaces/-web-eng-typescript (main) $ pnpm run start
$ tsx src/index.ts
キーボード 4800 2 true
10560
キーボードを2個購入する
税込合計は10560円である
2
Web Engineeringと2。
@4724228 ➜ /workspaces/-web-eng-typescript (main) $ git diff
diff --git a/src/index.ts b/src/index.ts
index 03486d1..026566b 100644
--- a/src/index.ts
+++ b/src/index.ts
@@ -26,3 +26,4 @@ let retryCount = 1;
 retryCount = 2;
 console.log(retryCount);
 
+console.log(`${courseName}と${retryCount}。`);

(`const`・`let`の違い)
constは一度値を代入すると、後から別の値を再代入することができない。 しかし、letは宣言した後でも別の値を再代入できる。
今回の実行では、constで宣言したcourseNameへの再代入はエラーになったが、letで宣言したretryCountは1から2へ再代入することができた。
