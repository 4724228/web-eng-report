#  第 7 回  Web エンジニアリング

  ##  学籍番号 
  4724228

  ## 2画面の見出しと本文（コードまたは確認結果）

const app = document.querySelector("#app");

if (app === null) {
    throw new Error("#app not found");
}

app.innerHTML = `
  <h1>画面生成方式の比較</h1>
  <p>この文章はTypeScriptから追加した。</p>

`;

window.addEventListener("hashchange", () => {
const page = location.hash;
console.log(page)
console.log(location.hash)

if (page === "#detail") {
    app.innerHTML = `
    <h1>詳細ページ</h1>
    <p>この文章はTypeScriptから追加した。</p>


`;
} else if (page === "#compare"){
   app.innerHTML = `
    <h1>比較ページ</h1>
    <p>この文章はTypeScriptから追加した。</p>

`;
}

});

  ##  クリック後のURLとNetworkの確認（コードまたは確認結果） 
確認できた。比較をクリックすると#compareのURLになり、詳細をクリックすると#detailのURLになった。

  ##  画面を切り替える処理の要点（コードまたは確認結果）
  window.addEventListener("hashchange", () => {
const page = location.hash;
console.log(page)
console.log(location.hash)

if (page === "#detail") {
    app.innerHTML = `
    <h1>詳細ページ</h1>
    <p>この文章はTypeScriptから追加した。</p>


`;
} else if (page === "#compare"){
   app.innerHTML = `
    <h1>比較ページ</h1>
    <p>この文章はTypeScriptから追加した。</p>

`;
}

});
