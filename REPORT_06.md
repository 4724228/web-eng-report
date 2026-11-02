# 第6回 Webエンジニアリング演習 レポート
## 学籍番号
4724228
## `Todo`型の定義
export type Todo = {
   id: number;
   title: string;
   completed: boolean;
dueDate?: string;
};
## 未完了件数を返す関数の引数と戻り値の型
export async function count(): Promise<number> {
const currentTodos = await fetchTodos();
const completeTodos =currentTodos.filter(
    (todo) => !todo.completed,
);
return completeTodos.length;
}
## 未完了件数の実行結果
@4724228 ➜ /workspaces/-web-eng-typescript (class-06-functions) $ pnpm run start
$ tsx src/index.ts
[
  { id: 1, title: '型を復習する', completed: true },
  { id: 2, title: '配列を学ぶ', completed: false },
  { id: 3, title: 'レポートを書く', completed: true },
  { id: 4, title: '宿題する', completed: true }
]
{ id: 2, title: '配列を学ぶ', completed: false }
未完了件数: 1