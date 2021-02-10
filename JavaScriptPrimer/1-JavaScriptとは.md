# JavaScriptとは
- JavaScriptは主にウェブブラウザで動くプログラミング言語である
  - ウェブサイトで操作をすることで表示を変更する
  - サーバーと通信してデータを取得する
  - JavaScriptを活用してアプリケーションのように操作できるウェブサイトをウェブアプリとも言う
  - Node.jsというサーバー側のアプリケーションを作る仕組みにも利用されている
  - デスクトップアプリやスマホアプリ, IoTデバイスでもJavaScriptを使用して動かすことができる
> JavaScriptは幅広い環境で動いているプログラミング言語で、様々な種類のアプリケーションを作成できる

## JavaScriptとECMAScript
- JavaScriptはECMAScriptという「どの実行環境でも共通の動作のみが定義されている」仕様によって動作が決められている
- 一方で、実行環境によって異なる部分があり、それらに必要な機能は実行環境ごとに定義されている
  - JavaScript: ブラウザでUIを操作する
  - Node.js: サーバー側の処理を書く
- ECMAScriptを学ぶことでどの実行環境でも対応できる基本部分を学ぶことができる
- ECMAScriptは毎年アップデートされ、新しい文法や機能が追加されている
  - ECMAScriptは2015年にES2015として大きくアップデートされた仕様が公開された

<img width="400" alt="
JavaScriptとECMAScriptのイメージ画像" src="https://jsprimer.net/basic/introduction/img/javascript-ecmascript.png">
> ECMAScriptはどの実行環境でも共通の部分、JavaScriptはECMAScriptと実行環境の固有機能も含んだ範囲というイメージ

## JavaScriptってどのような言語？
- JavaScriptは元々Nestscape Navigatorというブラウザのために開発された
- C, Java, Self, Schemeなどの言語に影響を受けて作られた
- JavaScriptは大部分がオブジェクト(値や処理を1つにまとめたもの)で、オブジェクト同士のコミュニケーションによって成り立っている
> ECMAScriptの仕様として定められたオブジェクト、実行環境が定めるオブジェクト、ユーザーの定めるオブジェクトが存在する

## 大文字と小文字を区別する
- JavaScriptは大文字小文字を区別する
  - 下記の場合、`name`と`NAME`はそれぞれ別々の名前の変数として認識される
```JavaScript
const name = "Kousuke";
const NAME = "Kousuke";
```
> 大文字で開始しなければならないという命名規則が意味を持つケースはない

## 予約語を持つ
- JavaScriotには予約語と呼ばれる特別な意味をもつキーワードがあり、このキーワードと同じ名前の変数や関数は宣言することができない

予約語一覧:
> break, case, do, if, switch, var, catch, else, in, this, void, continue, finally, instanceof, throw, while, default, for, new, try, with, let, debugger, const, export, class, extends, super, yield, import

将来の予約語一覧:
> abstract, double, implements, private, throws, boolean, enum, byte, protected, transient, char, interface, int, public, volatile, goto, package, synchronized, short, final, long, static, float, native

## 文はセミコロンで区切られる
- JavaScriptは文ごとに処理していき、セミコロン(;)によって区切られる
  - セミコロンがない文も、行末に自動でセミコロンが挿入される仕組みを持っているが、暗黙的な仕組みに頼ると意図しない挙動が起こるため、セミコロンは常に書くよう注意する
- スペース、タブ文字などは空白文字(ホワイトスペース)と呼ばれ、文にいくつ置いても挙動に違いはない
```JavaScript
// 式や文の間にスペースがいくつあっても同じ意味となる
1 + 1;
1   +   1;
```
> 空白文字の置き方は人により書き方が異なるため、複数人で開発する場合はコーディングスタイルを決める方がよい

## strict mode
- JavaScriptには**strict mode**という実行モードが存在する
  - 名の通り厳格な実行モードで、古く安全でない構文や機能が一部禁止される
- `use strict`という文字列をファイルまたは関数の先頭に置くことで、そのスコープにあるコードはstrict modeで実行される
  - "Module"の実行コンテキストでは、strict modeがデフォルトになっている
- 下記の例では、`const`などのキーワードを使用せず変数を宣言しようとすると、例外が発生する(strict modeでない場合は、例外が発生せずグローバル変数が作られる)
```JavaScript
"use strict";
// このコードはstrict modeで実行される
mistypedVariable = 42; // => ReferenceError
```
> strict mopdeでは`eval`や`with`などのレガシーな構文を禁止し、明らかな問題を含むコードに対しては早期に例外を投げることで開発者が間違いに気付きやすくするため、常にstrict modeで実行できるコードを書くべきである

## 実行コンテキスト:ScriptとModule
- Scriptの実行コンテキストは、多くの実行環境でデフォルトの実行コンテキストである
  - Scriptの実行コンテキストでは、デフォルトでstrict modeではない
- Moduleの実行コンテキストは、JavaScriptをモジュールして実行するためにES2015で導入された
  - Moduleの実行コンテキストでは、デフォルトがstrict modeとなり、古く安全でない構文や機能は一部禁止されている
  - モジュールの機能はModuleの実行コンテキストでしか利用できない
> JavaScriptの実行コンテキストにはScriptとModuleがあるが、コードを書く際に違いを意識することは多くない

## JavaScriptの仕様は毎年更新される
- JavaScriptの仕様であるECMAScriptは毎年更新され、JavaScriptには新しい構文や機能が増え続けている
- ECMAScriptは後方互換性が考慮されているため、過去に書いたJavaScriptのコードが動かなくなることはほとんどない
> 学んだことの全てが無駄になることはない
