# AWS DynamoDB
## テーブル
### テーブル名：PersonalityResults(診断結果)
|属性名|型|説明|
|---|---|---|
|userId|String|仮ユーザーID（UUID）|
|resultType|String|例：INTJ|
|resultTypeNum|Number|例:1|
|resultTime|Number|(UNIXタイムスタンプ)例：1713300000|
|resultJudge|Boolean|診断が終わったかどうか|
* パーティションキー：userId
* ソートキー:resultTypeNum

# ローカルストレージ
|キー名|型|用途|例|
|---|---|---|---|
|userId|Number|仮の一意ユーザID|uuidで発行して永続化|
|progress|dictionary|診断の進行状況|{ totalPoints: { E: 3, I: 2 } }|
|currentProgress|dictionary|現在答えた質問の種類|{Progress:{2,3,4,5,6}}|