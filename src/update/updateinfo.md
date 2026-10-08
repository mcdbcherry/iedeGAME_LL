<!-- iedegame-update: version=1.2610.0814 -->

<!-- iedegame-update: lang=ja -->

# iedeGAME サーバー 1.2610.0814

## 新しくなったところ

### 機種ごとの人気ゲームランキングを見られるようになりました

- ブラウザーの**ゲーム一覧の先頭に「ランキングを見る」**が出ます。押すと、その機種で
  人気・評価の高いゲームが順位付きで並びます。
- 並ぶのは**このサーバーにあるゲームだけ**です。持っていないゲームは出ません。
- それぞれに**短い紹介文**が付きます。「なぜ評価されているのか」が一覧のまま読めます。
- カードはいつものゲームのカードと同じです。**右クリック（長押し）のメニュー**も、
  詳細を見てからの起動も、これまでどおり使えます。
- 2回目以降は、**前の月からどれだけ順位が動いたか**（▲3 / ▼1 / NEW）も表示します。

### ランキングを使うには

- サーバーアプリのメニューに**「AI設定」**を追加しました。ここで**Gemini**または
  **OpenAI**を選び、APIキーを設定すると使えるようになります。
- **設定するまでは何も起きません。** ブラウザーにも「ランキングを見る」は出ず、
  外部への通信も一切行いません。
- 無料の範囲で使いたい場合は**Gemini**をお選びください。OpenAIには無料枠がありません。
- APIキーを入れたら**「接続を確認」**で試せます。うまくいかない場合は理由が表示されます。

### ランキングの更新について

- **月に1回**、月が替わって最初にサーバーアプリを起動したときに自動で作り直します。
  作成中はサーバーアプリのトップ画面に進行状況が出ます（そこから設定画面へ移れます）。
- 作成する機種は**チェックボックスで選べます**。アーケード基板は対象外です。
  1機種に何百もの作品と版違いが含まれ、家庭用ゲーム機ほど「人気ゲーム」の並びが
  意味を持たないためです。
- 機種ごとに**削除**して作り直せます。作成を**中止**することもできます。
- 改造版やHack版のROMは選ばれません。同じゲームのROMを複数お持ちの場合は、
  できるだけ**標準のROM**が選ばれます。

### ご注意

- 順位と紹介文は**AIがネット検索をもとに作ったもの**です。誤りが含まれることがあります。
  ランキングのページで、AIが参照した情報源をご確認いただけます。
- ランキングは、サーバーアプリの**「言語設定」**で選んだ言語で作られます。検索する
  情報源もその言語のものを優先します。ブラウザー側の表示言語とは別の設定なので、
  一致しないことがあります。

<!-- iedegame-update: lang=en -->

# iedeGAME Server 1.2610.0814

## What's new

### Popular game rankings for each system

- A **"View ranking"** link now appears at the top of each system's game list in the browser.
  It shows the most popular and highly rated games for that system, in order.
- Only games **held on this server** are listed. Games you do not have are left out.
- Each entry comes with a **short note** on why the game is well regarded, readable straight
  from the list.
- The cards are the same game cards as everywhere else. The **right-click (long-press) menu**
  and starting a game from its details work just as they do elsewhere.
- From the second month on, each entry also shows **how far it moved** since last month
  (▲3 / ▼1 / NEW).

### Turning rankings on

- A new **AI Settings** item was added to the server app menu. Choose **Gemini** or **OpenAI**
  there and enter an API key to enable the feature.
- **Nothing happens until you do.** The "View ranking" link stays hidden in the browser, and
  nothing is sent anywhere.
- Choose **Gemini** if you want to stay within a free quota. OpenAI has no free tier.
- After entering a key you can try it with **Check connection**. If it does not work, the reason
  is shown.

### How rankings are updated

- Rankings are rebuilt **once a month**, the first time the server app starts after the month
  changes. Progress is shown on the server app's main screen, with a shortcut to the settings.
- You can **pick which systems** get a ranking with checkboxes. Arcade boards are left out: one
  board holds hundreds of titles and many revisions of the same game, so a list of popular games
  means less there than it does for a home console.
- You can **delete** a system's ranking to have it rebuilt, and **stop** a build in progress.
- Hacked and modified ROMs are never chosen. When you hold several ROMs of the same game, the
  **standard one** is preferred.

### Please note

- The order and the notes are **produced by an AI from a web search**, so they can be wrong.
  The ranking page lists the sources the AI looked at.
- Rankings are written in the language chosen in the server app's **Language Settings**, and
  sources in that language are preferred. That is a separate setting from the display language
  in the browser, so the two may not match.
