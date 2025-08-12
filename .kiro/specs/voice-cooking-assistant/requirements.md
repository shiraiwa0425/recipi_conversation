# Requirements Document

## Introduction

音声対話型料理アプリケーションは、料理初級者から中級者をメインターゲットとし、音声による自然な対話を通じて料理をサポートするアプリケーションです。ユーザーは手が汚れた状態でも音声だけで操作でき、食材認識からレシピ提案、調理中のステップバイステップガイド、トラブルシューティングまで包括的にサポートします。特に忙しい現代人の料理効率化と、料理初心者の不安解消、キッチンでの孤独感軽減を目指します。

## Requirements

### Requirement 1

**User Story:** As a 料理初級者, I want 音声で食材を伝えるだけでレシピを提案してもらいたい, so that 冷蔵庫の食材を有効活用できる

#### Acceptance Criteria

1. WHEN ユーザーが音声で食材名を伝える THEN システム SHALL その食材を認識して記録する
2. WHEN 複数の食材を順番に伝える THEN システム SHALL 全ての食材をまとめて認識する
3. WHEN 「あと何がある？」と質問される THEN システム SHALL 追加食材の入力を促す
4. WHEN アレルギー食材や苦手な食材が登録されている THEN システム SHALL それらを除外したレシピを提案する

### Requirement 2

**User Story:** As a 料理をする人, I want 調味料の管理を自動化してほしい, so that 手持ちの調味料に合わせたレシピ提案を受けられる

#### Acceptance Criteria

1. WHEN 調理で調味料を使用する THEN システム SHALL その調味料を「所持している調味料」として自動記録する
2. WHEN ユーザーが所持調味料リストの確認を求める THEN システム SHALL 現在の調味料リストを音声で案内する
3. WHEN レシピ提案時 THEN システム SHALL 所持している調味料を前提とした提案を行う
4. WHEN 「この調味料持ってない」と伝える THEN システム SHALL 代替調味料を提案する

### Requirement 3

**User Story:** As a 料理初心者, I want 基本的な調理用語や技法を説明してほしい, so that 安心して料理に取り組める

#### Acceptance Criteria

1. WHEN 「包丁ってどう持つの？」などの基本質問をする THEN システム SHALL 分かりやすく説明する
2. WHEN 「塩少々って何グラム？」など曖昧な表現について質問する THEN システム SHALL 具体的な数値で回答する
3. WHEN 調理器具の使い方を質問する THEN システム SHALL 初心者向けに詳細説明する
4. WHEN 食材の見分け方を質問する THEN システム SHALL 選び方や状態判断方法を教える

### Requirement 4

**User Story:** As a 忙しい人, I want 状況に応じたレシピフィルタリングをしてほしい, so that 限られた時間で適切な料理を作れる

#### Acceptance Criteria

1. WHEN 料理の難易度を指定する THEN システム SHALL 指定レベルに適したレシピを提案する
2. WHEN 調理時間の制限を伝える THEN システム SHALL 時間内で完成するレシピのみ提案する
3. WHEN 「今日は疲れているから簡単なもの」と状況を伝える THEN システム SHALL 状況に適したレシピを提案する
4. WHEN 食事のタイプ（朝食、夕食など）を指定する THEN システム SHALL 該当するレシピを絞り込む

### Requirement 5

**User Story:** As a 調理中のユーザー, I want ステップバイステップで調理指導を受けたい, so that 失敗なく料理を完成させられる

#### Acceptance Criteria

1. WHEN 「次は何をすればいい？」と質問する THEN システム SHALL 次の調理手順を音声で案内する
2. WHEN 「もう一度教えて」と要求する THEN システム SHALL 前の手順を繰り返し説明する
3. WHEN 「ちょっと待って」と一時停止を要求する THEN システム SHALL 指示を停止して待機する
4. WHEN 調理のペースが遅い THEN システム SHALL ユーザーのペースに合わせて指示タイミングを調整する

### Requirement 6

**User Story:** As a 料理中のユーザー, I want 詳細な調理技術の説明を受けたい, so that 料理スキルを向上させられる

#### Acceptance Criteria

1. WHEN 調理手順の理由を質問する THEN システム SHALL なぜその手順が必要かを説明する
2. WHEN 包丁の使い方を質問する THEN システム SHALL 切り方の詳細な説明を提供する
3. WHEN 「もっと詳しく」と要求する THEN システム SHALL より詳細な調理テクニックを説明する
4. WHEN 料理の背景を知りたがる THEN システム SHALL 料理のルーツや文化的背景を説明する

### Requirement 7

**User Story:** As a 料理初心者, I want 失敗予防と安心サポートを受けたい, so that 不安なく料理に取り組める

#### Acceptance Criteria

1. WHEN 「これで大丈夫？」と不安を表明する THEN システム SHALL 現状確認と励ましを提供する
2. WHEN よくある失敗パターンが予想される THEN システム SHALL 事前に注意喚起する
3. WHEN 「初めて作るから心配」と伝える THEN システム SHALL 特に注意すべきポイントを強調する
4. WHEN 手順を間違えそうな時 THEN システム SHALL 「待って、先に〇〇をしましょう」と事前に止める

### Requirement 8

**User Story:** As a キッチンで作業するユーザー, I want 手が汚れていても音声だけで操作したい, so that 衛生的に料理を進められる

#### Acceptance Criteria

1. WHEN 騒がしいキッチン環境で音声入力する THEN システム SHALL 正確に音声を認識する
2. WHEN 方言や話し方の癖がある THEN システム SHALL 個人の話し方を学習して理解する
3. WHEN 子供が横から話しかける THEN システム SHALL メインユーザーの音声を識別する
4. WHEN 料理に関係ない質問をする THEN システム SHALL 失礼にならないよう軽く流して料理話題に戻す

### Requirement 9

**User Story:** As a 料理学習者, I want パーソナライズされた体験を受けたい, so that 効率的にスキルアップできる

#### Acceptance Criteria

1. WHEN よく作る料理がある THEN システム SHALL その料理を記憶して関連提案を行う
2. WHEN 家族の人数を伝える THEN システム SHALL 人数に合わせて分量を自動調整する
3. WHEN 過去の料理履歴を確認したい THEN システム SHALL 履歴を音声で案内する
4. WHEN 「前に作った〇〇のレシピ」と言う THEN システム SHALL 該当レシピを呼び出す

### Requirement 10

**User Story:** As a 料理中のユーザー, I want 調理中の問題を即座に解決したい, so that 料理を失敗せずに完成させられる

#### Acceptance Criteria

1. WHEN 「焦げそう」と緊急事態を伝える THEN システム SHALL 即座に対処法を案内する
2. WHEN 材料が足りない THEN システム SHALL 代替案を提案する
3. WHEN 「失敗した」と報告する THEN システム SHALL リカバリー方法を教える
4. WHEN 調味料の分量を間違える THEN システム SHALL 調整方法を指導する

### Requirement 11

**User Story:** As a 料理をする人, I want 食べ時と保存に関するアドバイスを受けたい, so that 料理を最適なタイミングで楽しめる

#### Acceptance Criteria

1. WHEN レシピ提案時 THEN システム SHALL 「できたてが一番美味しい」など食べ時を案内する
2. WHEN 水が出やすい食材を使う THEN システム SHALL 「作り置きには不向き」と事前に注意する
3. WHEN 時間を置いた方が良い料理 THEN システム SHALL 「一晩寝かせると美味しくなる」と案内する
4. WHEN 料理完成時 THEN システム SHALL 具体的な保存期間と再加熱のコツを教える

### Requirement 12

**User Story:** As a 複数の料理を同時に作るユーザー, I want タイマーと進行管理をサポートしてほしい, so that 効率的に調理を進められる

#### Acceptance Criteria

1. WHEN 「パスタ8分タイマー」と音声で設定する THEN システム SHALL 指定時間のタイマーを開始する
2. WHEN 複数のタイマーが動作中に「あと何分？」と質問する THEN システム SHALL 全タイマーの残り時間を案内する
3. WHEN 複数料理を同時進行する THEN システム SHALL 効率的な手順を組み立てて案内する
4. WHEN タイマーが終了する THEN システム SHALL 音声で通知して次の行動を指示する