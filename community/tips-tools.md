# 便利ツール・アセット情報

最終更新: 2026-07-19

VRChatアバター制作を効率化するコミュニティツールとその用途。

---

## 必須級ツール

### Modular Avatar
- **作者**: bd_
- **入手**: https://modular-avatar.nadena.dev/
- **用途**: アバターへのコンポーネント追加を非破壊的に行う
- **主要機能**:
  - MA Merge Armature: 衣装のボーンをアバターにマージ
  - MA Bone Proxy: ボーンの参照先を変更（v1.17.0 以降: **Match scale** オプション追加 — 参照先ボーンのスケールに自動的に合わせる）
  - MA Menu Installer: メニューを自動でRoot Menuに追加
  - MA Parameters: パラメータの自動登録
  - MA Blendshape Sync: ブレンドシェイプの同期
- **Write Defaults**: 自動的に整合性を取ってくれる
- **便利ショートカット**: Hierarchy上でアバターを右クリック → `Modular Avatar > Create Toggle` でオブジェクト切り替えトグルを素早く作成可能（出典: https://vrnavi.jp/modular-avatar-komono/）

### lilycalInventory
- **作者**: lilxyzw
- **入手**: https://github.com/lilxyzw/lilycalInventory
- **用途**: コンポーネントをGameObjectに追加するだけで衣装の着替え・トグルメニューを構築できるツール
- **主要コンポーネント一覧**:

| コンポーネント | 直接付与型 | 指定型 |
|-------------|----------|------|
| ON/OFF切り替え | `LI Prop` | `LI ItemToggler` |
| 択一選択（衣装切り替え） | `LI AutoDresser` | `LI CostumeChanger` |
| 数値スライダー操作 | `LI SmoothChanger` | — |
| メニューフォルダ階層化 | `LI MenuFolder` | `LI MenuFolder` |

- **Tips**: シェイプキーも同時操作可能。複数の衣装が入ったメニューは `LI MenuFolder` でフォルダ分類できる
- **出典**: https://note.com/khlizard/n/n3882666ea5c9

### VRCFury
- **入手**: https://vrcfury.com/
- **用途**: 非破壊的なアバター設定追加
- **主要機能**:
  - 衣装統合
  - Toggle自動生成
  - SkinnedMeshのArmature Link
- **Modular Avatarとの使い分け**: VRCFuryは衣装販売者向け機能が充実

### AvatarOptimizer (AAO)
- **作者**: anatawa12
- **最新バージョン**: 1.9.14
- **入手**: https://vpm.anatawa12.com/avatar-optimizer/
- **用途**: 非破壊的なアバター最適化
- **主要機能**:
  - Trace and Optimize: 未使用コンポーネント・ボーンを自動削除
  - Merge Skinned Mesh: SkinnedMeshを自動統合（Matcap/Emissionアトラスも可能）
  - Freeze Blendshape: 使わないBlendShapeを焼き込んでポリゴン削減
  - Merge PhysBone: 同設定のPhysBoneコンポーネントを統合してコンポーネント数を削減
  - **AAO Max Texture Size**: アバターのテクスチャ最大解像度を一括設定。例: 4K→1024pxに設定するとテクスチャメモリが59.81MB→11.25MBに削減（出典: https://vr-lifemagazine.com/avatar-optimizer-how-to/）
- **パフォーマンス改善効果**: 適切に設定すればEXCELLENT以上も狙える
- **出典**: https://vpm.anatawa12.com/avatar-optimizer/en/

---

## 作業効率化ツール

### FaceEmo
- **用途**: アバターの表情設定を専用UIで直感的に管理できるツール
- **特徴**: 各ジェスチャーに対応した表情クリップをGUI操作で割り当て可能
- **Tips**:
  - デフォルト表情は Archive 内に保存しておくことを推奨
  - `Open` 設定が Neutral 扱いされる（VRChat仕様）
  - Make It MMD と併用する場合は Write Defaults を全て ON に設定が必要
- **出典**: https://note.com/khlizard/n/n3882666ea5c9

### Light Limit Changer For MA v2
- **用途**: VRChat内でアバターのライト感度上限・下限を変更できるメニューを追加するツール
- **特徴**: v2が現在推奨版（v1より機能充実）。Modular Avatar対応で非破壊追加可能
- **出典**: https://note.com/khlizard/n/n3882666ea5c9

### Continuous Avatar Uploader
- **用途**: 複数のアバターバリアントを一括でビルド・アップロードするツール
- **活用場面**: Prefab Variant で複数の衣装バリアントを管理している場合に、全バリアントを一括アップロードできる
- **出典**: https://note.com/khlizard/n/n3882666ea5c9

### Gesture Manager
- Unity Editor上でジェスチャーをテスト再生できる
- PhysBoneの動作確認、表情の確認に便利

### VRChat SDK の Built-in Avatar Preview
- SDKビルドなしでPlayModeでアバターを確認
- PhysBone, Constraint の動作をEditor上で確認可能

### lilToon（シェーダー）
- VRChat最適化済みの高機能シェーダー
- マテリアルアトラス化機能内蔵
- MatCap, Emission, Dissolveなど多機能

### Poiyomi Toon（シェーダー）
- アニメーション連動機能が充実
- Locked / Unlocked モードに注意（Locked = 最適化済み）
- Animate With Properties でマテリアルのプロパティをアニメーション可能

---

## PhysBone設定補助ツール

### VRC Texture Optimizer
- **作者**: OXI Design
- **入手**: https://booth.pm/ja/items/6915386
- **用途**: VRChatアバターのテクスチャをバッチ一括最適化
- **主要機能**:
  - GPU ネイティブ圧縮（PC/Quest 両対応）
  - テクスチャ解像度・圧縮形式を一括最適化
- **効果**: テクスチャ容量・VRAM 使用量を大幅削減
- **価格**: 無料

出典: https://booth.pm/ja/items/6915386, https://vrnavi.jp/avatar-weight-saving1/

### PhysBone Tuner (コミュニティ製)
- PhysBoneの設定値をVisuallyプレビューしながら調整
- 具体的な数値の目安を提示してくれる

### Meshia Mesh Simplification
- **用途**: アバター全体のメッシュに対して一括ポリゴン削減
- **特徴**:
  - 目標パフォーマンスランクを指定すれば自動でポリゴン数を調整
  - AAOによる「削除」と違い「削減（間引き）」方式
  - lilNDMFMeshSimplifier の後継として現在主流
- **推奨箇所**: 単色パーツ・暗色パーツ・シンプルなメッシュ
- **避けるべき箇所**: 顔のまつ毛・髪の細部・指の関節など

出典: https://vrnavi.jp/avatar-weight-saving3/

### ActualPerformanceWindow（パフォーマンス確認ツール）
- **作者**: anatawa12
- **入手**: anatawa12のgistパック（VPM経由）
- **用途**: Unity Playモード内でアップロード後のパフォーマンス結果をリアルタイムプレビュー
- **効果**: AAOや各種最適化を適用した後の実際のランクをビルド前に確認できる

出典: https://vrnavi.jp/avatar-weight-saving3/

### KRT Material Tools
- **用途**: Unityのマテリアルを非破壊的に管理するツール
- **主要機能**:
  - **Quick Variant**: 選択したマテリアルを一括で Material Variant 化し、Prefab Variant にも自動で適用。元マテリアルを変更せず改変マテリアルを管理できる
- **活用シーン**: アバター衣装改変時に元アセットのマテリアルを汚さないよう、改変専用の Variant として分離する際に便利
- **出典**: https://zenn.dev/nekobox/articles/d0e92cb8a6f8ba

### ALCOM（VCC代替ランチャー）
- **用途**: VRChat Creator Companion (VCC) の代替アセット管理ツール
- **特徴**: 「かゆいところに手が届く」機能が充実しているとコミュニティで評価
- **主な利点**: パッケージ管理・バージョン管理をVCCより細かく制御可能
- 2026年時点でコミュニティの一部がVCCからALCOMへ移行中

出典: https://zenn.dev/exxxna/articles/a5cfff93823d8f

---

## Quest対応・アトラス化ツール

### TexTransTool（テクスチャアトラス化）
- **用途**: マテリアルのテクスチャを非破壊的にアトラス化（1枚のテクスチャに統合）するツール
- **主要機能**:
  - 複数マテリアルのテクスチャを自動で1枚にまとめ、Material Slots数を削減
  - NDMFパイプライン対応でModular Avatarと連携
  - Modular Avatar（v1.17.1+）ではTexTransToolの後に実行順が制御されている
- **v1.0.1以降の挙動変更（重要）**:
  - アトラス化とマテリアル統合が**分離**された仕様に変更
  - マテリアル統合時、「基準マテリアル」として指定したマテリアルの描画モード（Opaque/Cutout/Transparent）が統合後の全体に適用される
  - 透過設定のある部位（まつ毛・アイライン等）は基準マテリアルを Cutout または Transparent で設定する必要がある
- **活用場面**: Material Slotsを4個以下に削減してPC Excellentを目指す場合や、Quest対応時の素材統合
- 出典: https://vrc-db.com/optimize/, https://zenn.dev/augma/articles/5957851ecb4318

### XWear Packager（VRoid→VRChat変換）
- **用途**: VRoid Studio の XAvatar 形式アバターを VRChat 向け Unity プロジェクトにインポートするツール
- **特徴**:
  - VRM 形式経由ではなく XAvatar 形式を使う**公式推奨の変換フロー**
  - UniVRM（MToon10シェーダー必須）を導入した上で使用
  - VRoid Studio → 着せ替え機能 → XAvatarエクスポート → Unity で XWear Packager Window からインポート
- **注意**: インポート後、lilToon に切り替える際は描画モード（Opaque/Cutout/Transparent）を部位ごとに手動設定する必要がある
- **出典**: https://zenn.dev/augma/articles/5957851ecb4318

### VRCQuestTools（Quest対応変換）
- **用途**: VRChatアバターをAndroid/Quest対応に非破壊的に変換するツール
- **主要機能**:
  - PCシェーダー（lilToon・Poiyomi等）をQuest互換のToon Litシェーダーに自動変換
  - 非破壊的に変換されるため、元のPCアバター設定に影響なし
  - Avatar Descriptorの設定をそのまま引き継ぎ
- **活用場面**: PC用に作ったアバターをQuestユーザーにも表示させたい場合
- 出典: https://vrc-db.com/optimize/

---

## トラブルシューティング

### SDK「Missing Credentials」エラー

VRChat SDKのコントロールパネルで「Missing Credentials」が表示されアップロードできない場合の対処法。

**原因**: 2段階認証を設定している環境で、内部的に2段階認証が未実行の状態になっていることが多い。

**解決手順:**
1. Unity上の VRChat Control Panel → `Authentication` タブを開く
2. 「Logout」を選択して一度ログアウト
3. 再度アカウントにログイン（2段階認証コードを入力）

**上記で解決しない場合:**
- 各プロジェクトの `Logs` / `Library` フォルダを削除してUnityを再起動
- `User Settings` も削除する（環境に応じて）

出典: https://zenn.dev/yrd_gs/articles/b123e9fee91ff9

### Build & Test が通らない：Layers/Collision Matrix エラー

新規 Unity プロジェクトに VRChat SDK を追加した直後に発生するエラー。

**エラーメッセージ:**
> "You must address Layers and Collision Matrix issues before you can build."

**原因:** Project の Layer 設定と Collision Matrix が VRChat 向けに設定されていない状態。

**解決手順:**
1. VRChat SDK コントロールパネルで `Setup Layers for VRChat` ボタンをクリック
2. 確認ダイアログで「Do it!」を選択
3. 続いて `Collision Matrix` のセットアップボタンをクリック → 「Do it!」
4. 両方完了後、Build & Test を再実行

出典: https://zenn.dev/yazirushi/articles/f8f8c59c840826

### AAO Merge Skinned Mesh：Root Bone 未指定による消失バグ

**症状:** `Merge Skinned Mesh` でビルド後（または Play Mode 後）にメッシュが消失する。

**原因:** `Root Bone` が未指定（None）のままだと AAO がメッシュを正しく処理できない。

**解決策:** Merge Skinned Mesh コンポーネントの `Root Bone` に `J_Bip_C_Hips`（または対応するヒップボーン）を手動で指定する。自動検出されないため設定漏れに注意。

出典: https://zenn.dev/augma/articles/5957851ecb4318

---

## アバター管理ワークフロー

### Prefab Variant を使った複数衣装管理

複数の衣装・バリアントを効率よく管理するための推奨ワークフロー（2026年コミュニティ知見）。

**階層構造例:**
```
大元のPrefab / FBX
└─ ①基本設定済み Prefab Variant
   └─ ②共通アクセサリ付き Prefab Variant
      ├─ 衣装1 Prefab Variant
      ├─ 衣装2 Prefab Variant
      └─ ③シリーズ差分 Prefab Variant
```

**実作業ステップ:**
1. アバター基本設定（PB・Contacts・FX等）を完了 → Prefab Variant 化
2. 全衣装共通のアクセサリ・ギミックを追加 → 再び Variant 化
3. 差分ごとに Variant を分岐させ着せ替えを管理
4. `Continuous Avatar Uploader` で全 Variant を一括ビルド・アップロード

**メリット:**
- 基本設定の変更が全 Variant に自動反映される
- 衣装ごとの差分のみを編集すればよく、更新コストが低い

出典: https://note.com/khlizard/n/n3882666ea5c9

---

## パフォーマンスランク Excellent 達成の数値基準

VRChatアバターでExcellentランクを達成するための目安値（2026年時点）:

| 項目 | Excellent上限 |
|------|-------------|
| Triangles（ポリゴン数） | 32,000以下 |
| Texture Memory | 40MB以下 |
| Skinned Meshes | 1個以下 |
| Material Slots | 4個以下 |

**実践的な最適化フロー:**
1. `AAO Trace And Optimize` をアバタールートに追加（自動最適化）
2. lilAvatarUtils で4Kテクスチャを2Kに一括変換
3. Skinned Mesh を `AAO Merge Skinned Mesh` で統合（1〜2個に）
4. Material Slots を マテリアルアトラス化（lilToon/Poiyomiの機能）で4個以下に
5. `ActualPerformanceWindow` でビルド前にランクをプレビュー確認

出典: https://qiita.com/Hellcat_152/items/ad1b1ceb2504bc39c0a4

---

### PC/Quest デュアル最適化戦略

PC用アバターをQuestユーザーにも表示させる「PC/Questデュアル対応」には2種類のアプローチがある。

**Plan A（日常使い・見た目重視）**
- lilAvatarUtils で4Kテクスチャを2K以下に変換
- AAO Trace And Optimize で未使用ボーン・コンポーネントを削除
- VRCQuestTools でシェーダーをQuest互換に変換
- 目標: PC Good〜Excellent + Android Medium〜Poor

**Plan B（イベント特化・極限軽量化）**
- ポリゴン数: **20,000以下**（Android Poor上限。PC Excellentの32,000より厳しい）
- TexTransTool でテクスチャアトラス化し Material Slots を4個以下に
- ボーン数: **75個以下**（PC Excellent + Android Excellent 共通要件。`performance/ranking-system.md` 参照）
- PhysBone Components: **4個以下**（PC Excellent要件）
- VRCQuestTools でシェーダーをQuest互換に変換
- 目標: PC Excellent + Android Poor 同時達成

> **Android/Questのポリゴン制約はPCより大幅に厳しい**: Android Excellent=7,500 / Good=10,000 / Medium=15,000 / **Poor=20,000** トライアングルの制限がある。PC Excellent(32,000)に対してAndroid Poorが20,000と制約が強い。

出典: https://vrc-db.com/optimize/

---

## グループインスタンスのアバターパフォーマンス制限（2026.1.3）

VRChat バージョン **2026.1.3**（2026年4月9日リリース）で、グループインスタンス作成時にアバターの描画負荷の上限を設定できる「**アバター・パフォーマンス制限付きグループインスタンス**」機能が追加された。

### 機能概要

| 設定値 | 説明 |
|--------|------|
| **None（デフォルト）** | 制限なし。既存の動作と同じ |
| **Good** | Goodランク以上のアバターのみ通常表示 |
| **Medium** | Mediumランク以上のアバターのみ通常表示 |
| **Poor** | Poorランク以上のアバターのみ通常表示 |

- 上限を超えるアバターは **Impostor またはフォールバックアバター** として表示される
- グループロールで「制限バイパス権限」を付与できる（パフォーマー等の特例向け）
- デフォルトが None のため、設定を変更しない既存インスタンスには影響なし

**アバタークリエイターへの影響**: イベント主催者がGoodランク制限を設定するケースが増える可能性があり、配布アバターのパフォーマンス最適化の重要性が高まっている。PC Goodランク（Triangles 70,000以下 / PhysBone 8個以下 / Texture Memory 75MB以下）を意識した設計が推奨される。

出典: https://www.moguravr.com/vrchat-update-2026-1-3/

---

## VRChatのSDK更新チェック先

| リソース | URL | 内容 |
|---------|-----|------|
| 公式Changelog | https://creators.vrchat.com/releases/ | SDK更新履歴 |
| VRChat Blog | https://hello.vrchat.com/blog | 主要機能発表 |
| @VRChat_Dev (X) | https://x.com/vrchat_dev | 開発者公式アカウント |
| VRChat Discord | https://discord.gg/vrchat | Creator Channelが有用 |
| VRChat Canny | https://feedback.vrchat.com/ | バグ報告・機能要望 |

---

## バージョン・互換性情報

| 項目 | 現在の状況（2026-07-19時点） |
|------|---------------------------|
| 推奨Unity | 2022.3.x LTS |
| SDKバージョン（安定） | **3.10.4（2026-06-17リリース）** |
| Modular Avatarバージョン（安定） | 1.17.1（2026-05-14リリース）|
| Modular Avatarバージョン（アルファ） | 1.18.0-alpha.0（2026-05-31、未安定）|
| AvatarOptimizer (AAO) | 1.9.14 |
| SDK | VRChat Avatars 3.0 (VRCSDK3) |
| 旧SDK (VRCSDK2) | 廃止済み・アップロード不可 |
| Dynamic Bone | 非推奨。PhysBoneに移行推奨 |
| 新コンポーネント(SDK 3.10.3) | VRCRaycast（ワールド向け） |
| 新機能(SDK 3.10.4) | VRCTween（Udon向けトゥイーン）/ ボックス形状Contacts / グローバルPhysBoneコライダー（最大4個） |
| MA新コンポーネント(v1.13〜v1.15) | MA Rename VRChat Collision Tags / MA Move Independently / MA Global Collider / MA Platform Filter |
| MA新コンポーネント(v1.17.0) | MA Floor Adjuster（靴の床高さ自動調整） / VRCRaycastサポート / BlendShapeピッカーにマルチセレクト追加 |
| MA新機能(v1.18.0-alpha) | BlendShapeカーブリマッピング対応（アルファ段階） |

> **注意:** アルファ版は本番アバターへの使用非推奨。安定版リリース後に更新予定。

出典（SDK 3.10.4情報）: https://creators.vrchat.com/releases/release-3-10-4  
出典（MA 1.18 alpha情報）: https://github.com/bdunderscore/modular-avatar/releases
