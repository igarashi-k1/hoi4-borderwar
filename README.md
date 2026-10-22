# Border War Decisions (HOI4 MOD)

どの国でも、隣接する国にステートの割譲を要求し、拒否されたら国境紛争・宣戦布告で応じられるディシジョンを追加します。

## 流れ

1. 「国境紛争」カテゴリの **[ステート名]の割譲を要求** を実行（マップ上のステートから選択）
   - 対象：自国の所有ステートに隣接する他国のステートのうち、**所有国の中核州ではない**もの
   - 自国・相手国とも国境紛争中でなく、相手国と戦争中でないこと
2. 相手国にイベントが届き、受諾か拒否を選ぶ（AI は国力差を見て判断。自国の戦力が相手の半分未満だと受諾しやすい）
   - **受諾**：そのステートが自国に割譲される
   - **拒否**：要求した国にイベントが届き、次から選ぶ
     | 選択肢 | 効果 |
     | --- | --- |
     | 何もしない | 何も起こらない |
     | 国境紛争を開始する | 対象ステートと、それに隣接する自国ステートの間で国境紛争を開始 |
     | 宣戦布告する | 相手国に宣戦布告（戦争目標：全土併合） |
3. 国境紛争の結果
   - **勝利**：相手国のステートのうち、自国に隣接し相手国の中核州ではないものを**ランダムに1つ**獲得
   - **敗北・引き分け**：ペナルティなし（国境はそのまま）

## 補足

- 国境紛争は対象ステートと自国の攻撃側ステートに配置した師団で戦われます。開始前に攻撃側ステート（対象に隣接する自国ステート）へ師団を配置してください
- 要求中（返答待ち、最大60日）と国境紛争中は新たな要求を出せません
- 相手国が返答しないまま期限切れになった場合は「拒否」扱いになります
- 政治力コスト 0。AI は要求ディシジョンを使用しません（`ai_will_do = 0`）。AI は要求への返答のみ行います

## インストール

1. このフォルダを `Documents/Paradox Interactive/Hearts of Iron IV/mod/hoi4-borderwar/` に配置
2. 同じ `mod` フォルダに `hoi4-borderwar.mod` を作成し、以下を記述

```
version="1.0.0"
tags={
	"Gameplay"
}
name="Border War Decisions"
supported_version="1.*"
path="mod/hoi4-borderwar"
```

3. ランチャーで MOD を有効化

## 構成

```
descriptor.mod
common/decisions/categories/borderwar_categories.txt
common/decisions/borderwar_decisions.txt
events/borderwar_events.txt
localisation/english/borderwar_l_english.yml     (UTF-8 BOM付き)
localisation/japanese/borderwar_l_japanese.yml   (UTF-8 BOM付き)
```

※ ゲームの言語設定が日本語の場合は `l_japanese`（日本語）、英語の場合は `l_english`（英語）が使われます。日本語化MOD環境（英語設定）では英語で表示されます。
