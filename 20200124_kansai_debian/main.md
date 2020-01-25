
# リクルータからメールが来たら 

* 技術面接がある
    - コーディング
    - 実務的な問題

# ご注意

* レイヤーの高い Software Engineer を仮定しています 
* 低レイヤーの方や、Data Scientist の方、申し訳ありません

# 技術面接

* アルゴリズムとデータ構造
* システムデザイン 

# アルゴリズムとデータ構造

* 情報系の学部 1, 2 年の内容
* 加えて
    - コーディングの常識
    - プログラミング言語のシンタックス
* 競技プログラミング

# 例題: Two Sum

* 整数の数列 s と整数 k が与えられます。s の項を足して \
k になれば 'Yes' ならなければ 'No' を出力してください。

https://web.stanford.edu/class/cs9/sample_probs/SubarraySums.pdf

# 例題: Two Sum

* 入力
    - s = [1,7,3]
    - k = 8

* 出力
    - Yes

# 例題: Two Sum

* 入力
    - s = [1,7,3]
    - k = 6

* 出力
    - No

# 解答例: Two Sum

* 計算量が大きい解法も説明する。\
なぜ悪いか説明する。
* 最終的には最も計算量が小さいもの
    - 時間と空間の計算量を最小化

# 解答: Brutal Force

* 2 重のループを書いて探索  
    - s = [1,7,3]
    - k = 10

* 解法
    - {{1+7},{1+3},{7+1},{7+3}}
    - O(n^2)

# 解答例: Sort

* まずソートする
    - s = [1,3,7]
    - k = 10

* ペアのうち片方を決めたら 2 分探索
    - s[0] = 1  なし
    - s[1] = 3  --> 7
    - O(n log n)

# 解答例: Hash

* ハッシュに格納
    - s = [1,7,3]
    - k = 10

* ペアのうち片方を決めたら hash で探索
    - s[0] = 1  なし
    - s[1] = 3  --> 7
    - O(n)

# 練習する
* AtCoder
* Codeforce
* HackeRank
* LeetCode
* Aizu Online
* 世界で闘うプログラミング力\
を鍛える本

# システムデザイン

* インフラ的な設計
* 実務に近いアルゴリズム問題

# 例題
* ◯ouTube の人気動画ランキングを作る
* ◯itter のトレンド
* いわゆる Top k list 問題と言われるもの
* 分散しないと処理できないぐらいの\
アクセスがあると仮定

https://www.youtube.com/watch?v=kx-XDoPjoHw

# 解答方針: Top k list

* Lambda Architecture と呼ばれるもの
    - CAP 定理を最終的にだいたい満たす
    - 不正確だけど高速な処理系で streaming 処理  
    - 正確だけど低速な処理系で batch 処理

* How to beat the CAP Theorem

# 解答例 設計: パーティション

* リクエストを分割する
    - Consistent Hash, Proprtional Hash

\center
\includegraphics[scale=0.25]{lambda_arch01.png}

# 解答例 設計: Message Queue

* リスエストよりもスレッド数\
のほうが少ないので Queue がいる

\center
\includegraphics[scale=0.25]{lambda_arch02.png}

# 解答例 設計: Storage

* Fast Path は NoSQL (memory)  
* Slow Path は DB (file)

\center
\includegraphics[scale=0.25]{lambda_arch03.png}


# 解答例 Slow Path

* file に格納されたデータは\
バッチ処理される
* cron で 1 時間に一回起動とか

# 解答例 Slow Path
\center
\includegraphics[scale=0.25]{lambda_arch.png}

# 学ぶには

* System Design Primer
* System Design Interview (YouTube)
* 世界で闘うプログラミング力\
を鍛える本
