# p-B11 核融合発電 — 素人の思考実験

> 「考えるだけはただ。上手くいったらノーベル平和賞じゃね？」

## これは何？

素人エンジニアが Claude と一緒に「p-¹¹B 核融合で発電できないか」を真剣に考えた記録。

戦争ってエネルギー不足が根本にある気がして。  
そのへんにある水素とホウ素を核融合させるだけで無限にエネルギーが出るなら、世界変わるよね。  
バリムズい（SSS難易度）らしいけど、構造を理解するだけでも価値がある。

**思考ログ（Zenn スクラップ）→** [https://zenn.dev/good_relax/scraps/0a2d3a6003b2f0](https://zenn.dev/good_relax/scraps/0a2d3a6003b2f0)

---

## p-B11 とは

```
p  +  ¹¹B  →  3 × ⁴He  +  8.7 MeV
陽子   ホウ素11    ヘリウム×3
```

| 比較項目 | D-T（主流） | p-¹¹B（究極） |
|---------|-----------|------------|
| 中性子 | エネルギーの 80% が中性子 | ほぼゼロ |
| 放射性廃棄物 | 多い | ほぼなし |
| 燃料 | 三重水素は希少・放射性 | 水素 + 天然ホウ素（安価・豊富）|
| 直接発電 | 困難 | α粒子で原理的に可能 |
| 難易度 | 高い | 極めて高い |

---

## 現状の正直な評価

要問（yomons）フレームワークで分解した結果：

```
■ p-B11ルート（20問）+ D-Tルート（5問）= 合計25問
🟢 解決済み    2/25  タイミング同期、燃料供給
🟡 部分解決    7/25  安全の定義、燃料選択、方式選択 等
🔴 未解決     16/25  P_ie緩和、αチャネリング、壁耐久性、D-T工学問題 等
```

最上位の問い：**「そもそも p-B11 が最適燃料か？」**（L0 戦略層）
最大のボトルネック（p-B11ルート内）：**制動放射問題**（L1-2）
D-T が「十分安全かつ十分安価」なら、D-T が正解かもしれない。

詳細 → [`yomons/overview.md`](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/overview.md)

---

## リポジトリ構成

```
pb11-fusion/
├── yomons/          要問（答えを出す価値のある本質的な問い）の整理
├── approaches/      仮説・アプローチの置き場
├── simulations/     ブラウザで動くアニメーション（HTML）
└── references.md    参考文献
```

### コンテンツ一覧

解説（📄 .md）とアニメーション（▶ .html）のペア一覧。
.md は GitHub 上で読める。.html はブラウザで開くだけで動く（依存なし）。
要問の定義・フレームワークは [`yomons/README.md`](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/README.md) を参照。

**要問フレームワーク（レイヤー別）:**

| トピック | 解説 | アニメーション |
|---------|------|--------------|
| 要問ツリー全体・クリティカルパス | [📄 overview.md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/overview.md) | — |
| L1 物理層（クーロン障壁・制動放射・ローソン） | [📄 L1-physics.md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/L1-physics.md) | — |
| L2 工学層（タイミング・耐久・統合） | [📄 L2-engineering.md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/L2-engineering.md) | — |
| L3 材料層（壁劣化・汚染・液体金属） | [📄 L3-materials.md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/L3-materials.md) | — |
| L4 システム層（直接発電・収支・燃料） | [📄 L4-systems.md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/L4-systems.md) | — |

**物理の基礎概念:**

| トピック | 解説 | アニメーション |
|---------|------|--------------|
| Zピンチの原理・不安定性・対策 | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/zpinch.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/zpinch.html) |
| 二温度プラズマ（Ti/Te 分離） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/two-temp-plasma.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/two-temp-plasma.html) |
| マクスウェル vs 非マクスウェル分布 | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/maxwell-distribution.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/maxwell-distribution.html) |
| 制動放射（なぜ回収できないか） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/bremsstrahlung.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/bremsstrahlung.html) |
| 電荷中性・Z_eff | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/charge-neutrality.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/charge-neutrality.html) |
| ラーモア半径と電子排除 | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/larmor-radius.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/larmor-radius.html) |
| 核融合燃料の比較 | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/fuel-comparison.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/fuel-comparison.html) |
| 距離・時間スケ��ル | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/fusion-timescales.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/fusion-timescales.html) |
| ビーム-ターゲット核融合 | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/beam-target.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/beam-target.html) |
| 電子問題（なぜ電子が邪魔か・7つの対策） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/electron-problem.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/electron-problem.html) |
| P_ie問題とαチャネリング（真のボトルネック） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/pie-alpha-channeling.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/pie-alpha-channeling.html) |
| P_ieパルス計算（「一瞬のスキ」は存在しない） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/pie-pulse-calculation.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/pie-pulse-calculation.html) |
| p-B11プロジェクト別・電子対策比較 | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/pb11-electron-strategies.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/pb11-electron-strategies.html) |
| 量子力学的な裏技は使えるか？（全滅） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/quantum-tricks.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/quantum-tricks.html) |

**4サイクル方式の分析:**

| トピック | 解説 | アニメーション |
|---------|------|--------------|
| Ti/Te 分離の抜け道 | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/ti-te-escape.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/ti-te-escape.html) |
| 圧縮トポロジー（体→点の4ルート） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/compression-topology.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/compression-topology.html) |
| 電子排出メカニズム | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/electron-exhaust.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/electron-exhaust.html) |
| 4フェーズサイクル（フルアニメーション） | — | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/fusion-engine.html) |
| 3つの物理的障壁 | — | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/pb11-walls.html) |

**他プロジェクトとの比較:**

| トピック | 解説 | アニメーション |
|---------|------|--------------|
| 核融合プロジェクト比較（全25方式） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/fusion-projects.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/fusion-projects.html) |
| TAE Technologies | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/tae-technologies.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/tae-technologies.html) |
| Helion Energy | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/helion-energy.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/helion-energy.html) |
| MagLIF / Sandia | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/maglif.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/maglif.html) |
| LINEA（日本） | [📄 md](https://github.com/GoodRelax/pb11-fusion/blob/main/yomons/linea.md) | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/linea.html) |
| D-T vs p-B11 反応比較 | — | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/fusion-compare.html) |
| FRC の磁場反転配位 | — | [▶ html](https://goodrelax.github.io/pb11-fusion/simulations/frc.html) |

### approaches/（アプローチ）

要問に対する「仮説」の置き場。4サイクルはその一つに過ぎない。

| フォルダ | 内容 |
|---------|------|
| [`4cycle-pulsed/`](https://github.com/GoodRelax/pb11-fusion/blob/main/approaches/4cycle-pulsed/concept.md) | 電子ビーム集束 + Zピンチ爆縮の4フェーズ方式 |
| [`magnetic-confinement/`](https://github.com/GoodRelax/pb11-fusion/blob/main/approaches/magnetic-confinement/notes.md) | FRC・トカマク等（比較用メモ） |
| [`hybrid/`](https://github.com/GoodRelax/pb11-fusion/blob/main/approaches/hybrid/notes.md) | MagLIF・Helion 型等 |

---

## 生成環境

- **思考パートナー**: Claude Sonnet 4.6 → Opus 4.6 (Anthropic)
- **人間**: 素人エンジニア（物理専攻でもなんでもない）
- **スタンス**: 正しいかどうかより、構造を理解することに価値がある

物理・工学的な内容は Claude の知識に基づくが、**誤りが含まれる可能性がある。専門家の指摘歓迎。**

---

## ライセンス

MIT — 自由に使ってください。  
「これをベースに本当に核融合炉を作った」という報告も歓迎します。
