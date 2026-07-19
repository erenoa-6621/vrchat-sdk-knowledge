# Animator / FX Layer コミュニティTips

最終更新: 2026-07-19

---

## Write Defaults まとめ

### WD OFF が主流になった理由（コミュニティ知見）
- VRChatのデフォルトコントローラーはWD ONだが、カスタムLayerを追加するとWD混在になりやすい
- WD混在時の症状: 表情が0に戻る / トグルが反映されない / 他のレイヤーに干渉する
- 現在の主流: **全Layer全State WD OFF** で統一してアニメーションを明示的に制御

### WD OFF 実装の鉄則
1. 全Stateに明示的なアニメーションクリップを割り当てる
2. ON状態とOFF状態の両方のクリップを用意する
3. BlendTreeを使う場合、各MotionにWD OFFが適用されていることを確認

### ツールで一括対処
- **Modular Avatar**: WD整合性を自動管理
- **VRCFury**: WD設定を自動化
- **Av3 Creator**: WD一括チェック・修正機能あり

---

## FX Layer 実装Tips

### Any Stateを使ったトグル実装（推奨パターン）
```
Any State → Toggle_ON   : Condition MyParam == true
Any State → Toggle_OFF  : Condition MyParam == false
```
Transition Duration: 0, Has Exit Time: false にする。  
Can Transition To Self のチェックを外すと同じStateへの無駄な遷移を防げる。

### Transition の設定ミスを防ぐチェックリスト
- [ ] Has Exit Time: false（Conditionのみで遷移）
- [ ] Transition Duration: 0（即時切り替え）
- [ ] Interruption Source: Current State（意図しない割り込みを防ぐ）
- [ ] Can Transition To Self: オフ（同Stateへのループを防ぐ）

### アニメーションクリップの「None」は絶対に使ってはいけない
アニメーションクリップ内のプロパティで設定値が「None」のままになっていると、  
VRChat上でシェイプキーが正しく反映されないことがある。

**対処法:**
- None のフィールドは `proxy_empty` クリップ（VRCSDK 3.9.0+ 同梱）に置き換える
- または独自の空アニメーションクリップを作成して割り当てる
- 不要なレイヤー自体を削除するのが最もシンプルな解決策

出典: https://x.com/mimyquality/status/1822551094285021428

### FX Controller の Layer Weight 設定（重要・よくある落とし穴）
FX Controller に新しいレイヤーを追加した際、**デフォルトの Weight が 0** のままだとアニメーションが一切再生されない。

**確認手順:**
1. FX Controller をダブルクリックして Animator ウィンドウを開く
2. 追加したレイヤーの左側にある歯車アイコンをクリック
3. Weight が **1.0** になっていることを確認・変更する

出典: https://signyamo.blog/vrchat_playable-layers/

### パラメーター名の命名規則
アニメーターパラメーターの名前は **半角英数字とアンダースコアのみ** を推奨。
- 日本語などのマルチバイト文字は使用しないこと（ビルド後に認識されない場合がある）
- 大文字・小文字は区別される（`MyParam` と `myParam` は別のパラメーター）
- Expression Parameters と Animator Controller 両方で名前を完全一致させること

出典: https://note.com/ninado/n/nc1c5806ab024

### FloatパラメータをBlendTreeで使う
Toggleではなく滑らかな変化が必要な場合:
```
BlendTree (1D)
  Parameter: MyFloat
  0.0 → Normal.anim
  1.0 → Effect.anim
```
Radial Puppetと組み合わせて使うとメニューからスムーズに制御できる。

### 表情をGesture Layerに入れる vs FX Layer に入れる
| 方式 | メリット | デメリット |
|------|---------|----------|
| Gesture Layer | 直感的なジェスチャー制御 | Avatar Maskの設定が必要 |
| FX Layer | メニューから自由に制御 | ジェスチャーとの競合管理が必要 |
| 両方 | 最も自由度が高い | 設計が複雑になる |

---

## パラメータ設計Tips

### Bool vs Int どちらを使うか
| 用途 | 推奨型 |
|------|-------|
| ON/OFF切り替え | Bool (1bit) |
| 3種以上の選択肢 | Int (8bit) |
| 滑らかな変化 | Float (8bit) |

### ビット数節約
- 8つのToggleがある場合、8個のBool(8bit) vs 1個のInt(8bit)
  → 4つ以下なら Bool、5つ以上なら Int の方がビット効率が良い

### Saved vs 非Saved の判断基準
- 「次にVRChatを起動した時もその状態を維持したい」→ Saved: true
- 「毎回デフォルトから始まってほしい」→ Saved: false（エモート等）

---

## FX Layerテンプレートのベストプラクティス（2025年末以降）

### proxy_empty を使う（VRCSDK 3.9.0+）
従来のカスタム空アニメーションクリップ（`Custom_Empty.anim` 等）は  
VRCSDK同梱の **`proxy_empty`** クリップに置き換えることが推奨されている。

- `proxy_empty` は `Assets/VRCSDK/Examples3/Animation/ProxyAnim/proxy_empty.anim` に同梱
- VRCSDK 3.9.0 以上が必要
- みみーラボ製PlayableLayersテンプレートも2025年12月リリースのver 1.11.2でこれに対応済み（2026-06-29リリースの **ver 1.11.3** でベースレイヤー遷移条件のアップライトしきい値を調整）

出典: https://booth.pm/ja/items/4301775

### Is Animated フラグの適切な活用
FX Layer内でPhysBoneのパラメータ（掴み状態等）をアニメーションクリップで制御している場合は  
PhysBoneの `Is Animated` を **ON** にする必要がある。  
それ以外の場合は **OFF** にすることでパフォーマンスが向上する。

---

## Animator Layer の構成ベストプラクティス

```
FX Controller の Layer 構成例:

[0] Base Weight
[1] Toggle - Item A   (Weight: 1.0)
[2] Toggle - Item B   (Weight: 1.0)
[3] Toggle - Outfit   (Weight: 1.0)
[4] Expression        (Weight: 1.0)
[5] Gesture Face      (Weight: 1.0)
[6] Audio             (Weight: 1.0)
```

- 各機能を別Layerに分けることでデバッグが容易
- Layer 0のBase Weightは基本的に変更しない
- 新機能追加時は新Layerを末尾に追加（既存への影響を最小化）

---

## FX表情制御の高度な実装パターン

### 右手優先表情システム
複数ジェスチャーでの表情制御では「右手優先」設計にすることで自然な操作感を実現できる:
- 左手入力中に右手を動かすと `Input(R) > 0` の条件でサブステートマシンを即座に抜け、右手の入力を優先する
- 左手はモーション（歩行等）兼用のため誤作動が起きやすく、右手が明示的に操作された場合は常に右手を優先する設計が推奨される

### リップシンク中の表情変更を防ぐ
表情遷移の Condition に `Voice < 0.01` を追加することで、発話中（リップシンク動作中）に表情が切り替わるのを防ぐことができる。  
`Voice` パラメータはマイク音量に応じて 0.0〜1.0 で変化するビルトインパラメータ。

### Contact連動 Override変数
`FaceNo(Override)` のような上書き変数を設定しておくと、Contact（タッチ入力）連動で特殊表情を強制適用できる。  
例: 「撫でられ中は全表情を照れ顔に固定する」「特定の状況ではジェスチャー入力を無視する」といった拡張が可能。

出典: https://note.com/x9n_note/n/nb77cf6b53e74

---

## MA Reactive コンポーネントを使った衣装トグル実装パターン

FX Layerを直接編集せずに衣装のトグル・シェイプキー連動・貫通防止を実装できるパターン。

### 1. オブジェクト ON/OFF（MA Object Toggle）
```
衣装Prefab/
  [MA Menu Item] → DressEnabled (Toggle)
  [MA Object Toggle]
    Object: 衣装メッシュ
    Active: true（DressEnabled=ON のとき表示）
```

### 2. ボディのシュリンク連動（MA Shape Changer）
```
衣装Prefab/
  BodyAdjust/
    [MA Shape Changer]
      Target: アバター/Body (SkinnedMeshRenderer)
      Blendshape: "衣装A_補正" → 100
    ↑ 衣装ONの時のみ自動適用。アニメーター不要
```

### 3. シュリンクBlendShapeがない場合（MA Mesh Cutter）
```
衣装Prefab/
  PenetrationFix/
    [MA Mesh Cutter]
      Target: アバター/Body (SkinnedMeshRenderer)
      ← マスクテクスチャで削除範囲を指定 (By Maskモード)
```
衣装ONの時だけ貫通部分の頂点をビルド時に削除できる。

### 4. コンポーネントを衣装オブジェクトに集約するパターン
複数のリアクティブコンポーネントを衣装GameObject直下にまとめることで  
「このオブジェクトがアクティブな時にこれらを実行する」という管理が明確になる。

出典: https://kxn4t.hatenablog.com/entry/2026/01/26/163232

---

## VRC Constraints 実装Tips

### VRC Parent Constraint の基本設計原則

`VRC Parent Constraint` はTransform階層を変えずにTargetの位置・回転を制御するコンポーネント。Unityの親子付けや `MA Bone Proxy` と混同しないこと:

| コンポーネント | 役割 |
|------------|------|
| MA Bone Proxy | 配置・追従先の変更（静的） |
| VRC Parent Constraint | 動的な状態制御・切り替え |

### 推奨オブジェクト構造（アイテム制御）

```
D_Transform_Hand_R   ← 追従基準
└── D_Constraint_Hand_R   ← Constraint制御
    └── D_Pivot_Hand_R    ← 見た目回転用Pivot
        └── Model
```

**Constraint対象を直接回さない**: 見た目の回転は子の Pivot GameObject に委ねること。Constraint対象を直接回転させると Freeze To World 時に想定外の挙動が起きる。

### 重要な設定項目

| 項目 | 説明 |
|------|------|
| **Weight** | Source からの影響量。左右持ち替えはこれを切り替えて実装 |
| **Freeze To World** | ワールド基準で固定する（「停止」ではなく「固定」）。解除するとアバターに追従再開 |
| **Rebake Offsets When Unfrozen** | 固定解除時に Offset を焼き直すか。ON推奨 |
| **Axis Exclusion** | 特定軸をConstraintの評価から除外できる |

### 左右持ち替えパターン

RightHandとLeftHandをSourceに指定し、それぞれの Weight をFXレイヤーでアニメーション制御する:

```
Source[0]: RightHand  Weight: 1.0 → 0.0（右→左に切り替える）
Source[1]: LeftHand   Weight: 0.0 → 1.0
```

**注意**: 複数の切り替えを同一フレームで行わず、段階的に処理することで安定性が向上する。

出典: https://zenn.dev/yrd_gs/articles/80a2a8d965ebbb

---

### 表情制御における Any State の使いどころ

**トグル（ON/OFF切り替え）には Any State が適切**:
```
Any State → Toggle_ON   : Condition MyParam == true
Any State → Toggle_OFF  : Condition MyParam == false
```

**ただし多段階の表情制御では Any State を避けること**:  
`Any State` からの遷移はすべてのConditionが**毎フレーム評価**されるため、状態が多いほどCPU負荷が高くなる。  
ジェスチャー表情（8ジェスチャー×両手など多数の状態）には以下パターンを推奨:

```
Entry → Idle → [表情ステート] → Exit
```

この設計では現在のステートから次のステートへの遷移のみが評価される。  
また、**FX Layer全体ではマスクを使わない**こと（Gesture Controllerの指アニメーションと競合する）。

出典: https://vrclibrary.com/wiki/books/blus-avatar-creation-standards/page/section-3-animator-controllers-and-you

---

## MA Mesh Settings を使った Anchor Override 一括設定

アバター全体の Skinned Mesh Renderer に `Anchor Override` を一括適用するための手法。個別に設定するより効率的で、後から追加したパーツにも自動適用される。

**手順:**
1. アバタールート（またはメッシュ群の親）に `MA Mesh Settings` コンポーネントを追加
2. `Anchor Override` を `Set` モードに設定
3. 参照先に `J_Bip_C_Hips`（ヒップボーン）を指定

**効果:**
- Skinned Mesh の Anchor Override が統一され、照明・シェーダーのバウンディングボックスが安定する
- VRoid 系アバターや多数の Skinned Mesh が分割されているアバターで特に有効

出典: https://zenn.dev/augma/articles/5957851ecb4318
