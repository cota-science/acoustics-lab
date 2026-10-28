# 音響ラボ

弦や管の固有振動から生まれる「倍音」を手がかりに、音色・和音のハモり・替え指の使い分けを、見て、鳴らして確かめる Web 教材です。吹奏楽・弦楽の部員向け。[物理基礎ラボ](https://cota-science.github.io/basicphysics-review/)・[物理ラボ](https://cota-science.github.io/physics-lab/) とは独立したサイトです。

- 公開ページ：https://cota-science.github.io/acoustics-lab/
- ビルド不要。HTML ファイルをそのまま GitHub Pages（main / root）で配信します
- 音は Web Audio API で合成します（音符やボタンを押してから鳴ります）

## 学習コース（トップページ）

高校の物理を習っていない部員を想定し、1→4 の順に進めます。

1. 音は波：`anim/wave-model.html` `anim/wave-model-l.html` `anim/longitudinal.html` `anim/wave-speed.html`
2. 楽器の中の定在波（定常波）：`anim/transverse.html` `anim/string.html` `anim/air-column.html`
3. 音色と聞こえ方：`anim/timbre.html`（`#add` `#mic` `#vowel`）`anim/beats.html` `anim/hearing.html`
4. 演奏に生かす：下の2つのアプリ

`anim/` の10ページは物理基礎ラボ（cota-science/basicphysics-review の `anim/`）のコピーです。音響ラボ用に次の点だけ変えています。

- 先頭に「物理を習っていない人へ」の案内（わかること・ことばと記号・楽器とのつながり・まずやってみよう）を追加
- 戻るリンクを「‹ 音響ラボ」に、ナビの「アニメーション集」を「音響ラボ」「音のことば」に変更し、「波を3次元で見る」を外した

物理基礎ラボ側を直したときは、そのページをコピーし直して同じ変更を加えます（案内の文章は `words.html` と同じ言い回しにそろえる）。マイク（`timbre.html#mic`）は https のページでのみ使えます。

## アプリ

| ページ | 内容 |
|---|---|
| `harmony-lab.html` 倍音ハーモニーラボ | 和音の各声部の倍音を並べ、うなりと差音から純正な音程を探す。平均律／純正律／ピタゴラス律、セント単位の微調整、耳だけで合わせるモード |
| `brass-map.html` 金管倍音マップ | B♭トランペット・ホルン（F／B♭／ダブル）・トロンボーン（テナー／バス F トリガー）・ユーフォニアム（3本／4本／コンペンセーティング）・チューバ（3本／4本）の押さえ方ごとの倍音列（第12倍音まで）を五線譜で表示。替え指ファインダー、倍音マップ、スライド位置 |

## フォルダ構成

```
index.html         トップページ（学習コースとアプリ）
words.html         音のことば（記号の読み方と用語集）
anim/              物理基礎ラボから取り込んだ音・波のアニメーション（10ページ）
harmony-lab.html   倍音ハーモニーラボ（1ファイルで完結）
brass-map.html     金管倍音マップ（1ファイルで完結。ト音・ヘ音記号と♯♭は SVG パスで埋め込み）
.nojekyll          GitHub Pages で Jekyll を通さない
```

## アプリを追加するとき

1. 新しい HTML ファイルを1つ作る（既存の2ファイルと同じ色とフォントの変数 `:root` を使う）
2. ページ先頭の `<header>` に `<a class="backlink" href="./">← 音響ラボ</a>` を入れる
3. `index.html` の学習コース「4 演奏に生かす」にカードを1枚追加し、「これから追加する予定」から外す

## 用語と表記

- 「定在波（定常波）」と書く
- 音程のずれはセント（半音の 1/100）。平均律を基準に、低めを青、高めを橙で表示する
- 金管倍音マップの上ずりの値は、チューニング管を調整しない場合の理論値
