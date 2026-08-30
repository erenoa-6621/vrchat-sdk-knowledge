# ナレッジベース更新履歴

VRChat SDK & Modular Avatar ナレッジベースの週次更新記録。

---

## 2026-08-30

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **v1.18.4（安定版）リリース**: 2026-08-29（前回v1.18.3から1バージョンアップ）
  - **Unity 6.1〜6.7への実験的サポート追加**（v1.18.4最大のアップデート）
  - Unity 6.2+ での MeshLOD 処理を修正
  - MA Blendshape Sync: メッシュ関連エラーを修正
  - MA Mesh Cutter: 空メッシュ処理の問題を修正
  - MA Material Setter: 負のマテリアルスロット問題を修正
  - Shape Changer / Mesh Cutter: プレビュー更新の不具合を修正
  - Sync Parameter Sequence: 設定参照問題を修正
  - エディタ操作の取り消し機能とプレハブインスタンス変更の保存問題を修正
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- 新規追加なし（今週の検索では既存エントリと重複のみ）

### 更新ファイル一覧

- `community/tips-tools.md`: MA v1.18.4リリース情報をバージョンテーブルに追加、最終更新日を2026-08-30に更新
- `modular-avatar/overview.md`: Unity 6.1〜6.7実験的サポートを必須要件セクションに追記、最終更新日を2026-08-30に更新

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-08-23

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **v1.18.2（安定版）リリース**: 2026-08-18
  - VRCSDK 3.7.0でのコンパイルエラーを修正

- **v1.18.3（安定版）リリース**: 2026-08-21（前回v1.18.1から2バージョンアップ）
  - バグ修正: メッシュカッター・シェイプチェンジャーを異なるスケールの本体と衣装に適用した際のメッシュ歪みを修正（スケール差のある衣装改変時の重要修正）
  - BlendShape Syncアニメーション互換性の改善
  - プレイモード時のメッシュ適用バグを修正
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- **MA Mesh Cutterで帽子着用時の髪貫通を防ぐワークフロー**（`community/tips-tools.md` Modular Avatarセクションに追加）
  - MeshDeleter with Texture（Booth有料）で貫通箇所をマスクテクスチャとして書き出し → 帽子オブジェクトのMA Mesh CutterにBy Maskで適用
  - 帽子をトグルOFFした際に元の髪型が自動復元されるのが最大のメリット
  - 出典: https://zenn.dev/exxxna/articles/e3ce757509850f

### 更新ファイル一覧

- `community/tips-tools.md`: MAバージョンをv1.18.3に更新、v1.18.2・v1.18.3バグ修正情報をバージョンテーブルに追加、MA Mesh Cutter帽子/髪貫通対策TipsをModular Avatarセクションに追加（最終更新日更新）
- `modular-avatar/overview.md`: 最終更新日を2026-08-23に更新

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-08-16

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.18.1（2026-08-03）**: 前回から変更なし
- Merge Armature・Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- **Editor Logでアップロードファイルの容量割合を確認する手法**（`community/tips-tools.md` パフォーマンスランクセクションに追加）
  - Console→三点メニュー→Open Editor Log を開き、`prefab.unity3d` を検索することでアセット別の容量割合を一覧確認できる
  - 最適化前の優先順位決定に活用。「テクスチャが80%を占める」等が分かれば、テクスチャ圧縮ツールを先に実施することで効率的に削減できる
  - 出典: https://posfie.com/@ron2kt/p/xaGWbuO

### 更新ファイル一覧

- `community/tips-tools.md`: Editor Logによる容量割合可視化Tipsを追加、バージョンテーブル日付を2026-08-16に更新（最終更新日更新）

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Modular Avatar v1.18.1（安定版）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-08-09

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **v1.18.0（安定版）リリース**: 2026-08-02（前回 alpha.0 段階から正式安定版に昇格）
  - 新コンポーネント **MA Outfit Root**: 衣装プリファブのルートオブジェクトをマーク。Setup Outfit 実行時に MA Scale Adjuster の値をベースアバターから衣装へ自動コピー
  - 新機能 **MA Move To**: ビルド時にオブジェクトを指定の階層位置へ移動させる機能
  - **MA Blendshape Sync** カーブリマッピングが正式対応（アルファ段階から昇格）
  - 頂点フィルター強化: UV タイル選択・マスク内の代替 UV チャンネル選択が可能に

- **v1.18.1（安定版）リリース**: 2026-08-03
  - バグ修正: Reaction Debugger を開く際の NullReferenceException を解決
  - パフォーマンス改善: Scale Adjuster プレビューの動作速度を向上

- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- WebSearch 実施: 新規の有用な Tips は確認できず（既存エントリと重複のみ）

### 更新ファイル一覧

- `modular-avatar/overview.md`: MA Outfit Root・MA Move To を「衣装管理系（v1.18.0+）」セクションとして新規追加、最終更新日更新
- `community/tips-tools.md`: バージョンテーブルを v1.18.1（安定版）に更新。アルファ行を削除し v1.18.0/v1.18.1 の新機能行を追加、最終更新日更新

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-08-02

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし（2026-05-14リリースのまま）
- **v1.18.0-alpha.0**: アルファ版のまま変更なし（安定版リリース待ち）
- Merge Armature・Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- **かろやかテクスチャ**（`community/tips-tools.md` Quest対応・アトラス化ツールセクションに新エントリ追加）
  - 2026年6月配布開始の無料テクスチャ軽量化ツール
  - ワンクリックで容量を約40%カット。顔・瞳を自動保護、Quest対応、原本復元機能付き
  - NDMFパイプライン対応
  - 出典: https://luminance1116.booth.pm/items/8480183

- **NDMF ExMenu Organizer**（`community/tips-tools.md` 作業効率化ツールセクションに新エントリ追加）
  - ドラッグ＆ドロップでエクスプレッションメニューを非破壊的に並べ替え・フォルダ化
  - 削除アイテムの未使用パラメーターを自動削除してアバターメモリを節約
  - ¥500、MA+NDMF必須
  - 出典: https://booth.pm/ja/items/7841621

- **NDMF RemoveFX**（`community/tips-tools.md` 作業効率化ツールセクションに新エントリ追加）
  - 不要なFXレイヤーをチェックボックス選択で非破壊削除
  - 削除レイヤーでしか使われていないパラメーターも自動削除
  - 購入アバターの不要ギミックFXを衣装改変後に安全除去する用途に最適
  - ¥300、NDMF必須
  - 出典: https://booth.pm/ja/items/7861390

### 更新ファイル一覧

- `community/tips-tools.md`: かろやかテクスチャ・NDMF ExMenu Organizer・NDMF RemoveFX の新エントリ追加、バージョン情報テーブルの日付を更新（最終更新日・バージョンテーブル更新）

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Modular Avatar v1.17.1（安定版）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-07-26

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし（2026-05-14リリースのまま）
- **v1.18.0-alpha.0**: アルファ版のまま変更なし（安定版リリース待ち）
- Merge Armature・Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- **LAC: Avatar Compressor**（`community/tips-tools.md` 新セクション追加）
  - テクスチャを非破壊で圧縮するツール。プリセット「Balanced」が基本設定
  - ジャギが目立つ場合は「Quality」プリセットへ変更、または問題テクスチャを「Freeze」（圧縮対象外）に設定
  - 推奨解像度: 細かい模様は 2K/1K、その他は 512 以下
  - lilycalInventory の LI AutoFixMeshSettings と組み合わせることでライティング最適化も同時実行可能
  - 出典: https://note.com/_aono_/n/n5c879d9f43ea

- **lilycalInventory「LI AutoFixMeshSettings」の詳細**（`community/tips-tools.md` 既存セクションに補完）
  - アバタールートに追加するだけでメッシュ設定を自動調整するコンポーネント
  - 上級設定で「update when offscreen」をオフに設定（オフスクリーン時の描画負荷削減）
  - Anchor Override を Hips（Armature/Hips）に一括設定
  - 「Prefab [General] Optimize」: マテリアル最適化 / 「Prefab [lilToon] Fix Lighting」: lilToon専用ライティング修正
  - 出典: https://note.com/_aono_/n/n5c879d9f43ea

- **アバター改変後の素体変形問題**（`community/tips-tools.md` トラブルシューティングに追加）
  - 原因: 元アバターのFX Layerに含まれる衣装干渉対策シェイプキーアニメーションが改変後も動作し続ける
  - 解決法1: AAO「Freeze BlendShape」で問題のシェイプキーを選択固定
  - 解決法2: AAO「Trace And Optimize」がアニメーションのないシェイプキーを自動検出して固定
  - 注意: 顔パーツのシェイプキーには適用しないこと（表情が壊れる）
  - 出典: https://zenn.dev/narutoo/scraps/3beac50057c7ae

### 更新ファイル一覧

- `community/tips-tools.md`: LAC: Avatar Compressor 新エントリ追加、lilycalInventory に LI AutoFixMeshSettings 詳細を補完、アバター素体変形問題のトラブルシューティングを追加（最終更新日・バージョンテーブル更新）

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Modular Avatar v1.17.1（安定版）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-07-19

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（最終更新 2026-06-17）: 変更なし
- Contacts仕様（最終更新 2026-06-17）: 変更なし
- Constraints仕様（最終更新 2025-10-08）: 変更なし
- Playable Layers（最終更新 2025-12-05）: 変更なし
- Animator Parameters（最終更新 2025-12-12）: IsAnimatorEnabled・IsOnFriendsListを含め変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし（2026-05-14リリースのまま）
- **v1.18.0-alpha.0**（2026-05-31）: アルファ版のまま変更なし
- Merge Armature・Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- **グループインスタンスのアバターパフォーマンスランク制限**（`community/tips-tools.md` 新セクション）
  - VRChat 2026.1.3（2026年4月9日）で追加された機能
  - グループインスタンス作成時にGood/Medium/Poorの3段階でアバターパフォーマンスの下限を設定可能
  - 上限超えのアバターはImpostorまたはフォールバック表示。デフォルトはNone（制限なし）
  - PC Goodランク要件（Triangles 70k以下 / PhysBone 8個以下 / Texture Memory 75MB以下）を意識した設計の重要性が高まっている
  - 出典: https://www.moguravr.com/vrchat-update-2026-1-3/

- **VRC Constraints 実装Tips**（`community/tips-animator-fx.md` 新セクション）
  - VRC Parent Constraintの基本設計原則: Bone Proxy（静的配置）と混同しないこと
  - 推奨オブジェクト構造: D_Transform → D_Constraint → D_Pivot（見た目回転）→ Model の4層
  - 左右持ち替えパターン: SourceのWeight切り替えで実装し、複数切り替えは段階的に処理
  - Freeze To World は「停止」ではなく「ワールド基準での固定」
  - 出典: https://zenn.dev/yrd_gs/articles/80a2a8d965ebbb

- **表情制御でのAny State最適化**（`community/tips-animator-fx.md` 既存セクションに補完）
  - Any Stateは単純ON/OFFトグルには適切だが、多段階の表情制御（8ジェスチャー等）では毎フレーム全Conditionが評価されるためCPU負荷が高い
  - 多状態の表情制御には Entry → Idle → 表情ステート → Exit のパターンを推奨
  - FX Layer全体でマスクを使わないこと（Gesture Controllerの指アニメーションと競合する）
  - 出典: https://vrclibrary.com/wiki/books/blus-avatar-creation-standards/page/section-3-animator-controllers-and-you

### 更新ファイル一覧

- `community/tips-tools.md`: グループインスタンスのパフォーマンスランク制限セクションを追加、バージョン情報テーブルの日付を更新（最終更新日更新）
- `community/tips-animator-fx.md`: VRC Constraints 実装Tipsセクションを追加（左右持ち替えパターン・設計原則・Any State最適化を含む）（最終更新日更新）

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Modular Avatar v1.17.1（安定版）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-07-12

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters（IsAnimatorEnabled・IsOnFriendsList含む）: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし（2026-05-14リリースのまま）
- **v1.18.0-alpha.0**（2026-05-31）: アルファ版のまま変更なし。安定版リリース待ち
- Merge Armature・Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- **lilycalInventory** 新エントリ（`community/tips-tools.md`）
  - コンポーネント追加で衣装のON/OFF・択一切り替え・数値スライダーメニューを構築できるツール（lilxyzw作）
  - LI Prop / LI ItemToggler / LI AutoDresser / LI CostumeChanger / LI SmoothChanger / LI MenuFolder の使い分けを表で整理
  - 出典: https://note.com/khlizard/n/n3882666ea5c9

- **FaceEmo** 新エントリ（`community/tips-tools.md`）
  - 表情設定を専用GUIで直感的に管理できるツール。Make It MMD 併用時は Write Defaults 全て ON が必須
  - 出典: https://note.com/khlizard/n/n3882666ea5c9

- **Light Limit Changer For MA v2** 新エントリ（`community/tips-tools.md`）
  - VRChat内でライト感度上限・下限を変更できるメニューを非破壊追加するツール（v2推奨）
  - 出典: https://note.com/khlizard/n/n3882666ea5c9

- **Continuous Avatar Uploader** 新エントリ（`community/tips-tools.md`）
  - Prefab Variant で管理する複数アバターを一括ビルド・アップロードできるツール
  - 出典: https://note.com/khlizard/n/n3882666ea5c9

- **TexTransTool v1.0.1+ 挙動変更**（`community/tips-tools.md` TexTransTool欄を更新）
  - アトラス化とマテリアル統合が分離された仕様に変更
  - 基準マテリアルの描画モード（Opaque/Cutout/Transparent）が統合後全体に適用される点に注意
  - 出典: https://zenn.dev/augma/articles/5957851ecb4318

- **XWear Packager**（VRoid→VRChat変換）新エントリ（`community/tips-tools.md`）
  - VRoid Studio の XAvatar 形式を Unity にインポートする公式推奨フロー（VRM経由より推奨）
  - 出典: https://zenn.dev/augma/articles/5957851ecb4318

- **Build & Test Layers/Collision Matrix エラー** 対処法追記（`community/tips-tools.md` トラブルシューティング）
  - 新規プロジェクトで "You must address Layers and Collision Matrix issues before you can build." が出る場合の解決手順
  - 出典: https://zenn.dev/yazirushi/articles/f8f8c59c840826

- **AAO Merge Skinned Mesh Root Bone 未指定バグ** 追記（`community/tips-tools.md` トラブルシューティング）
  - Root Bone を手動指定しないとビルド後にメッシュが消失する問題と解決策（J_Bip_C_Hips を指定）
  - 出典: https://zenn.dev/augma/articles/5957851ecb4318

- **Prefab Variant を使った複数衣装管理** ワークフロー追記（`community/tips-tools.md`）
  - 基本設定→共通アクセサリ→衣装差分という3層 Variant 構造と Continuous Avatar Uploader 連携フロー
  - 出典: https://note.com/khlizard/n/n3882666ea5c9

- **MA Mesh Settings Anchor Override 一括設定** 追記（`community/tips-animator-fx.md`）
  - MA Mesh Settings コンポーネントを使って Anchor Override を Set モード + J_Bip_C_Hips で全メッシュに一括適用するワークフロー
  - 出典: https://zenn.dev/augma/articles/5957851ecb4318

### 更新ファイル一覧

- `community/tips-tools.md`: lilycalInventory・FaceEmo・Light Limit Changer For MA v2・Continuous Avatar Uploader・XWear Packager 新エントリ追加、TexTransTool v1.0.1+ 挙動変更追記、Build & Test/AAO Merge Skinned Mesh トラブルシューティング追加、Prefab Variant ワークフロー追加（最終更新日更新）
- `community/tips-animator-fx.md`: MA Mesh Settings Anchor Override 一括設定を追記（最終更新日更新）

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Modular Avatar v1.17.1（安定版）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-07-05

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし（2026-05-14リリースのまま）
- **v1.18.0-alpha.0**（2026-05-31）: アルファ版のまま変更なし。安定版リリース待ち
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- **Playable Layers Template v1.11.3 更新**（2026-06-29）
  - ベースレイヤー遷移条件のアップライトしきい値を調整
  - `community/tips-animator-fx.md` の該当箇所を v1.11.3 に更新
  - 出典: https://booth.pm/ja/items/4301775

- **MA Mesh Cutter** ドキュメント化
  - MA v1.12.0+ で追加済みだが当ナレッジベースに未記載だったコンポーネントを追記
  - 衣装貫通防止のためにメッシュ頂点をビルド時に削除する機能。BlendShapeがない場合のMA Shape Changerの代替
  - By Maskモード: マスクテクスチャ（白=削除対象）で削除範囲を指定
  - 更新ファイル: `modular-avatar/components/reactive.md`（新セクション追加）、`modular-avatar/overview.md`（コンポーネント一覧に追記）
  - MA Reactiveコンポーネントの組み合わせパターン（Object Toggle + Shape Changer + Mesh Cutter）を `community/tips-animator-fx.md` に追記
  - 出典: https://kxn4t.hatenablog.com/entry/2026/01/26/163232

### 更新ファイル一覧

- `community/tips-animator-fx.md`: Playable Layers Template v1.11.3 更新記録、MA Reactiveコンポーネント組み合わせパターンを追記（最終更新日更新）
- `modular-avatar/components/reactive.md`: MA Mesh Cutter セクションを新規追加
- `modular-avatar/overview.md`: MA Mesh Cutter をコンポーネント一覧に追記（最終更新日更新）
- `community/tips-tools.md`: バージョン表の日付を更新（最終更新日更新）

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Modular Avatar v1.17.1（安定版）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-06-28

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4**: 前回から変更なし（2026-06-17リリース済み）
- PhysBone仕様（グローバルコライダー含む）、Contacts（ボックス形状含む）、Constraints（6種類）、Playable Layers、Animator Parameters: 変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし（2026-05-14リリースのまま）
- **v1.18.0-alpha.0**（2026-05-31）: アルファ版のまま変更なし。安定版リリース待ち
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- `community/tips-tools.md` に以下を追記（最終更新日も更新）:

  - **TexTransTool**（新ツールエントリ）
    - マテリアルのテクスチャを非破壊的にアトラス化（1枚のテクスチャに統合）するツール
    - NDMFパイプライン対応でModular Avatarと連携
    - 出典: https://vrc-db.com/optimize/

  - **VRCQuestTools**（新ツールエントリ）
    - PCアバターをAndroid/Quest対応に非破壊変換
    - lilToon・Poiyomi等のシェーダーをQuest互換Toon Litに自動変換。元のPC設定に影響なし
    - 出典: https://vrc-db.com/optimize/

  - **PC/Questデュアル最適化戦略**（新セクション）
    - Plan A（日常使い）: lilAvatarUtils + AAO + VRCQuestTools。目標 PC Good〜Excellent + Android Medium〜Poor
    - Plan B（イベント特化）: TrianglesをAndroid Poor上限20,000以下に、Bones 75個以下（PC Excellent要件）、Material Slots 4個以下（TexTransToolでアトラス化）、PhysBone 4個以下
    - Androidのポリゴン制約（Poor=20k）がPC Excellent（32k）より厳しいことを解説
    - 出典: https://vrc-db.com/optimize/

### 更新ファイル一覧

- `community/tips-tools.md`: Quest対応ツール（TexTransTool・VRCQuestTools）新エントリと、PC/Questデュアル最適化戦略を追記（最終更新日更新）

### 確認済み・変更なし

- VRChat SDK 3.10.4（安定版）: 変更なし
- PhysBone仕様（Version 1.0/1.1、グローバルコライダー含む）: 変更なし
- Contacts仕様（ボックス形状含む）: 変更なし
- Constraints仕様（6種類）: 変更なし
- Playable Layers仕様: 変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 変更なし
- Modular Avatar v1.17.1（安定版）: 変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-06-21

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.4（安定版）** リリース確認（2026-06-17）: 前回 3.10.3 からメジャーアップデート
  - 出典: https://creators.vrchat.com/releases/release-3-10-4

- **VRCTween 追加**（ワールド/Udon向け）
  - DOTweenライブラリをUdonに公開。位置・回転・スケールのアニメーション補間が可能
  - キャンセル可能な遅延呼び出し機能も含む
  - ※アバターではなくワールド開発向け機能

- **ボックス形状Contacts対応**（新機能）
  - VRCContactSender / VRCContactReceiverに `Box` 形状が追加
  - 幅（Width）・高さ（Height）・奥行き（Depth）を個別設定可能（各最大6m）
  - `Use Face Proximity` オプション（Receiver専用）: ボックスの+Z面までの距離でProximity計算。ボックス中心ではなく面への最接近距離を返すため精密な接触判定が可能
  - 更新ファイル: `components/contacts.md`

- **グローバルPhysBoneコライダー**（新機能）
  - VRCPhysBoneColliderに `Global Collision` オプション追加
  - ONにすると他アバターやワールドのPhysBoneとも衝突するグローバルコライダーになる
  - **制限**: アバター1体あたり最大4個、SphereとCapsuleのみ対応（Plane不可）
  - 6個超過時は指コライダーを「奪う」（Ring指→小指→中指の順）
  - 更新ファイル: `components/physbones.md`

- その他の変更（ワールド/Udon向け）:
  - PhysBoneコライダーのUdon動的制御対応
  - データコンテナにEnsureCapacityメソッド追加
  - VRCPickup追加時に自動でPickupレイヤーに移動
  - シェーダーチャンキング（4MB単位）を全プロジェクトで実装

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし
- **v1.18.0-alpha.0**（2026-05-31）: アルファ版のまま変更なし
  - 安定版リリース待ち
  - 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- WebSearch が今回結果を返さなかったため、新規Tipsの追加なし

### 更新ファイル一覧

- `components/contacts.md`: ボックス形状対応を追記（最終更新日更新）
- `components/physbones.md`: グローバルコライダー仕様を追記（最終更新日更新）
- `community/tips-tools.md`: SDKバージョンを 3.10.4 に更新（最終更新日更新）

### 確認済み・変更なし

- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし（グローバルコライダーは新機能として追記）
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 前回から変更なし
- Modular Avatar v1.17.1（安定版）: 前回から変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-06-14

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**: 安定版は前回から変更なし
- **SDK 3.10.4-beta.3**（2026-06-11）: ベータ版がリリース中。安定版への昇格待ち
  - 詳細な変更内容は安定リリース時に改めて記録予定
  - 出典: https://creators.vrchat.com/releases/
- PhysBone仕様、Contacts、Constraints、Playable Layers、Animator Parameters: 変更なし

### Modular Avatar（公式ドキュメント確認）

- **最新安定版 v1.17.1**: 前回から変更なし
- **v1.18.0-alpha.0**（2026-05-31）: アルファ版がリリース中
  - **BlendShapeカーブリマッピング対応**（Added support for remapping blendshapes using a curve）
  - Mesh Cutterプレビューのパフォーマンス改善
  - Scale Adjusterプレビュー更新の修正
  - **注意**: アルファ版のため本番アバターへの使用非推奨
  - 出典: https://github.com/bdunderscore/modular-avatar/releases

### コミュニティTips

- `community/tips-physbone.md` に以下を追記（最終更新日も更新）:

  - **VRChat内でのPhysBone診断方法**（新セクション）
    - ExMenu → オプション → アバター → アバターのオーバーレイ → PhysBones で視覚的に確認可能
    - 白い線（ボーンチェーン）と半透明球体（掴み・衝突判定）の見方を解説
    - 出典: https://note.com/kalkal_vrc/n/nc5145318f864

  - **PhysBoneが揺れない・掴めない場合の診断フロー**（新セクション）
    - 揺れない: リーフボーンがない場合はEndpoint Position（非ゼロ値）またはBlenderでリーフボーン追加
    - 全員が掴めない: Radius=0 / Allow Grabbing=False の見落としが多い
    - 特定の人だけ掴めない: 相手のインタラクト許可範囲設定を確認
    - 出典: https://note.com/kalkal_vrc/n/nc5145318f864, https://note.com/oyajik/n/n584365cc6b93

- `community/tips-tools.md` に以下を更新（最終更新日も更新）:

  - **バージョン・互換性情報テーブル** を更新
    - SDK 3.10.4-beta.3（2026-06-11）をベータ版として記録
    - MA 1.18.0-alpha.0（2026-05-31）をアルファ版として記録
    - MA 1.18 alpha の新機能「BlendShapeカーブリマッピング」を追記

### 確認済み・変更なし

- VRChat SDK 3.10.3（安定版）: 前回から変更なし
- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters: 前回から変更なし
- Modular Avatar v1.17.1（安定版）: 前回から変更なし
- Merge Armature、Menu Installer: 変更なし

---

## 2026-06-07

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**: 前回から変更なし
- PhysBone仕様、Contacts、Constraints、Playable Layers、Animator Parameters: いずれも変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新バージョン v1.17.1**: 前回から変更なし（2026-05-14 リリース済み）
- Merge Armature、Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- `community/tips-animator-fx.md` に以下を追記（最終更新日も更新）:

  - **FX表情制御の高度な実装パターン**（新セクション）
    - 右手優先表情システム: `Input(R) > 0` 条件でサブステートマシンを即座に抜け右手入力を優先する設計
    - リップシンク中の表情変更を防ぐ `Voice < 0.01` 条件の活用法
    - Contact連動 Override変数（例: `FaceNo(Override)`）でタッチ連動表情制御を実現するパターン
    - 出典: https://note.com/x9n_note/n/nb77cf6b53e74

- `community/tips-tools.md` に以下を追記（最終更新日も更新）:

  - **AAO Max Texture Size** 機能を AvatarOptimizer の説明に追記
    - テクスチャ最大解像度一括設定機能。4K→1024pxで59.81MB→11.25MBに削減する効果
    - 出典: https://vr-lifemagazine.com/avatar-optimizer-how-to/

  - **KRT Material Tools**（新ツールエントリ）
    - Quick Variant機能: マテリアルを一括でMaterial Variant化し元アセットを汚さず改変を管理
    - 出典: https://zenn.dev/nekobox/articles/d0e92cb8a6f8ba

### 確認済み・変更なし

- VRChat SDK 3.10.3: 前回から変更なし
- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 前回から変更なし
- Modular Avatar Merge Armature、Menu Installer: 前回から変更なし

---

## 2026-05-31

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**: 前回から変更なし
- PhysBone仕様、Contacts、Constraints、Playable Layers、Animator Parameters: いずれも変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新バージョン v1.17.1**: 前回から変更なし（2026-05-14 リリース済み）
- Merge Armature、Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/docs/changelog

### コミュニティTips

- `community/tips-physbone.md` に以下を追記（最終更新日も更新）:

  - **Simplified モード 黄金比クイックリファレンス**（新セクション）
    - ふわふわ系（髪・ケモ耳）: Pull 0.1 / Spring 0.6 / Immobility 0.3
    - ぷるぷる系（胸・柔らかい肉）: Pull 0.1 / Spring 0.8 / Immobility 0.5
    - ひらひら系（スカート・布）: Pull 0.2 / Spring 0.4 / Immobility 0.6
    - 出典: https://vrc-step.com/vrc-avatar-physbones/

  - **掴み・固定の制御（新セクション）**
    - Allow Posing = false で他ユーザーのポーズ固定を禁止
    - **複数PhysBoneで構成される部位は全コンポーネントに同一設定が必要**（よくある抜け漏れ）
    - 出典: https://vrnavi.jp/physbone-fix/

  - **パフォーマンス節約テクニック**に `AAO Merge PhysBone` を追記

- `community/tips-tools.md` に以下を更新（最終更新日も更新）:

  - **AvatarOptimizer (AAO) にバージョン情報 1.9.14 を追記**
    - 主要機能に `Merge PhysBone` を追加
    - 出典: https://vpm.anatawa12.com/avatar-optimizer/en/

  - **バージョン・互換性情報テーブル** に `AvatarOptimizer (AAO) 1.9.14` 行を追加

### 確認済み・変更なし

- VRChat SDK 3.10.3: 前回から変更なし
- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 前回から変更なし
- Modular Avatar Merge Armature、Menu Installer: 前回から変更なし

---

## 2026-05-24

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**: 前回から変更なし
- PhysBone仕様、Contacts、Constraints、Playable Layers、Animator Parameters: いずれも変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新バージョン v1.17.1**: 前回から変更なし（2026-05-14 リリース済み）
- 出典: https://modular-avatar.nadena.dev/docs/changelog

- **v1.17.0 追記漏れを補完: MA Bone Proxy に Match Scale オプション追加**
  - Bone Proxy コンポーネントに「Match scale」オプションが追加（v1.17.0）
  - 参照先ボーンのスケールに自動的に合わせる機能
  - `community/tips-tools.md` の MA Bone Proxy 説明行に追記

### コミュニティTips

- `community/tips-animator-fx.md` に以下を追記（最終更新日も更新）:

  - **FX Controller の Layer Weight 設定（よくある落とし穴）**
    - FX Controller に新しいレイヤーを追加した際、デフォルトの Weight が 0 のままだとアニメーションが一切再生されない
    - Animator ウィンドウで歯車アイコン → Weight を 1.0 に設定すること
    - 出典: https://signyamo.blog/vrchat_playable-layers/

  - **パラメーター名の命名規則**
    - 半角英数字とアンダースコアのみ推奨（日本語などのマルチバイト文字は不可）
    - 大文字・小文字は区別される
    - 出典: https://note.com/ninado/n/nc1c5806ab024

### 確認済み・変更なし

- VRChat SDK 3.10.3: 前回から変更なし
- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 前回から変更なし
- Modular Avatar Merge Armature、Menu Installer: 前回から変更なし

---

## 2026-05-17

### Modular Avatar（公式ドキュメント確認）

- **バージョン更新: v1.16.2 → v1.17.1**
  - 出典: https://modular-avatar.nadena.dev/docs/changelog

- **v1.17.0**（2026-05-11）主な変更点:
  - 新コンポーネント `MA Floor Adjuster` 追加: 靴底がワールドの床に合うようアバターの垂直位置を自動調整
  - VRCRaycastコンポーネントとパラメータのサポート追加（SDK 3.10.3の新コンポーネントに対応）
  - BlendShapeピッカーにマルチセレクト機能追加

- **v1.17.1**（2026-05-14）:
  - MA Floor Adjuster の実行順序を修正: TexTransToolなど既存のNDMFプラグインの後に実行されるように変更

- 更新ファイル:
  - `modular-avatar/overview.md`: MA Floor Adjusterをコンポーネント一覧に追記
  - `modular-avatar/components/floor-adjuster.md`: 新規作成
  - `community/tips-tools.md`: バージョン情報を v1.17.1 に更新、新コンポーネント情報追記

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**: 前回から変更なし
- PhysBone仕様、Contacts、Constraints、Playable Layers、Animator Parameters: いずれも変更なし
- 出典: https://creators.vrchat.com/releases/

### コミュニティTips

- `community/tips-tools.md` に以下を追記:

  - **SDKトラブルシューティング: Missing Credentials エラー対処法**
    - VRChat Control Panel → Authentication → Logout → 再ログインで解決するケースが多い
    - Logs/Library フォルダ削除で解決する場合もある
    - 出典: https://zenn.dev/yrd_gs/articles/b123e9fee91ff9

  - **パフォーマンスランク Excellent の数値基準**
    - Triangles 32,000以下 / Texture Memory 40MB以下 / Skinned Meshes 1個以下 / Material Slots 4個以下
    - AAO + lilAvatarUtils + ActualPerformanceWindowを組み合わせた最適化フロー
    - 出典: https://qiita.com/Hellcat_152/items/ad1b1ceb2504bc39c0a4

### 確認済み・変更なし

- VRChat SDK 3.10.3: 前回から変更なし
- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 前回から変更なし
- Modular Avatar Merge Armature、Menu Installer: 前回から変更なし

---

## 2026-05-10

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**: 前回から変更なし
- PhysBone仕様、Contacts、Constraints、Playable Layers、Animator Parameters: いずれも変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新バージョン v1.16.2**: 前回から変更なし（2026年2月11日リリースのまま）
- Merge Armature、Menu Installer: 変更なし
- 出典: https://modular-avatar.nadena.dev/

### コミュニティTips

- `community/tips-tools.md` に以下3ツールを追記:

  - **Meshia Mesh Simplification**: アバター全体のメッシュを一括ポリゴン削減するツール。目標パフォーマンスランクを指定して自動調整。lilNDMFMeshSimplifierの後継として現在主流。
    - 出典: https://vrnavi.jp/avatar-weight-saving3/

  - **ActualPerformanceWindow**: Unity Playモード内でアップロード後のパフォーマンス結果をリアルタイムプレビューできるツール（anatawa12作）。
    - 出典: https://vrnavi.jp/avatar-weight-saving3/

  - **ALCOM**: VCC（VRChat Creator Companion）の代替アセット管理ランチャー。2026年時点でコミュニティの一部がVCCからの移行を進めている。
    - 出典: https://zenn.dev/exxxna/articles/a5cfff93823d8f

### 確認済み・変更なし

- VRChat SDK 3.10.3: 前回から変更なし
- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters（IsAnimatorEnabled、IsOnFriendsList含む）: 前回から変更なし
- Modular Avatar Merge Armature、Menu Installer: 前回から変更なし

---

## 2026-05-03

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**: 前回から変更なし
- PhysBone仕様、Contacts、Constraints、Playable Layers、Animator Parameters: いずれも変更なし
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **最新バージョン v1.16.2**（2026年2月11日リリース）を確認
  - 出典: https://modular-avatar.nadena.dev/docs/changelog

- 未記載だった新コンポーネントを `modular-avatar/components/vrchat-specific.md` に追記:
  - **MA Rename VRChat Collision Tags**（v1.13.0+）
    - ContactsのCollision Tagを自動的にユニーク名にリネーム
    - 複数の配布Prefabが同じタグ名を使っても誤検出されなくなる
    - 出典: https://modular-avatar.nadena.dev/docs/reference/rename-collision-tags
  - **MA Move Independently**（エディタ専用ユーティリティ）
    - 子オブジェクトを動かさずに親オブジェクトのみを移動できる
    - 衣装のHipボーン位置微調整に有用
    - 出典: https://modular-avatar.nadena.dev/docs/reference/move-independently

- `modular-avatar/overview.md` のコンポーネント一覧に上記2コンポーネントを追記
- `community/tips-tools.md` のバージョン情報を更新（MA v1.16.2 を追記）

### 確認済み・変更なし

- VRChat SDK 3.10.3: 前回から変更なし
- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters: 前回から変更なし
- Modular Avatar Merge Armature、Menu Installer: 前回から変更なし

---

## 2026-04-26

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3** が最新バージョンであることを確認（前回から変更なし）
- 出典: https://creators.vrchat.com/releases/

### Modular Avatar（公式ドキュメント確認）

- **Merge Armature** の Lock Mode 名称を公式ドキュメントに合わせて修正
  - `Base Path` → `単方向`、`Both Paths` → `双方向` に更新
  - 新パラメータを `modular-avatar/components/merge-armature.md` に追記:
    - Reset Position オプション（Also set rotation / Also set local scale / Adjust outfit overall scale）
    - Avoid name collisions（デフォルト ON）
    - Adjust bone names to match target
  - 出典: https://modular-avatar.nadena.dev/docs/reference/merge-armature

### コミュニティTips

- `community/tips-physbone.md`: ふんわりスカート（Hinge型）設定と足コライダー配置を追記
  - Hinge 制限でのスカート設定値（Pull/Momentum/Immobileのカーブ活用）
  - スカート貫通防止のための足コライダー推奨配置（UpperLeg/LowerLeg）
  - 出典: https://note.com/x9n_note/n/nb45abf2f9e5a, https://cgbox.jp/2023/09/01/vrchat-physbone-howto/

- `community/tips-animator-fx.md`: アニメーションクリップの "None" 使用禁止Tipを追記
  - None → `proxy_empty` または空クリップへの置き換え推奨
  - 出典: https://x.com/mimyquality/status/1822551094285021428

- `community/tips-tools.md`: VRC Texture Optimizer を追記
  - GPU ネイティブ圧縮、PC/Quest 両対応の無料テクスチャ最適化ツール
  - 出典: https://booth.pm/ja/items/6915386, https://vrnavi.jp/avatar-weight-saving1/

### 確認済み・変更なし

- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Animator Parameters: 前回から変更なし（ドキュメント最終更新 2025-12-12）
- Modular Avatar Menu Installer: 前回から変更なし

---

## 2026-04-19

### VRChat SDK（公式ドキュメント確認）

- **SDK 3.10.3**（2026-04-16リリース）を確認
  - 新コンポーネント `VRCRaycast` の導入（ワールド向け）
  - Toon Standardの改善
  - UdonへのVRC+サブスクリプション状態の公開
  - 出典: https://creators.vrchat.com/releases/

- **新ビルトインパラメータ**を `animations/animator-parameters.md` に追記
  - `IsAnimatorEnabled`（Bool）: アニメーター有効/無効状態の検出
  - `IsOnFriendsList`（Bool）: 着用者がフレンドリストにいるか判定
  - 出典: https://creators.vrchat.com/avatars/animator-parameters/

- **Expression Parameters**の仕様補足を追記
  - 最大登録数 8192個（256bit制限内）
  - マルチプラットフォーム時はリスト順・型の一致が必須（名前では同期しない）

### コミュニティTips

- `community/tips-animator-fx.md`: FX Layerテンプレートのベストプラクティスを追記
  - `proxy_empty`（VRCSDK 3.9.0+）の使用推奨
  - `Is Animated` フラグの適切な活用
  - 出典: https://booth.pm/ja/items/4301775

- `community/tips-tools.md`: Modular Avatarの便利ショートカットを追記
  - Hierarchy右クリック → `Modular Avatar > Create Toggle` で素早くトグル作成
  - 出典: https://vrnavi.jp/modular-avatar-komono/
  - SDKバージョン情報を 3.10.3 に更新

### 確認済み・変更なし

- PhysBone仕様（Version 1.0/1.1）: 前回から変更なし
- Contacts仕様: 前回から変更なし
- Constraints仕様（6種類）: 前回から変更なし
- Playable Layers仕様: 前回から変更なし
- Modular Avatar（Merge Armature、Menu Installer）: 前回から変更なし
