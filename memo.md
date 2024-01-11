やること
* StreamDiffusion

データの販売
教会、病室、日常系詰め合わせ（自宅、古い家、ショッピング施設）
線画、


## 販売済
1. 昭和風花柄　サムネ直す？
落ち着いたバー、夜のお店
パステルカラー水玉


* faceswap
素材によって出来上がりが結構違う。
もともとやせ型の人の場合、skinny, lanky を入れると顔も痩せて本人ぽくなる
濃い目のメイクの画像はepic系と相性がいい？
アジア系の強い顔だとどんくさい感じになる。おそらくCodeFormerのせい？ 

# 元絵画像のコツ
どっかの写真集の画像をひろってきたほうが安定した構図になる

ランダム姿勢、場所、服、色、などをするには？  プラグイン使う？
LoRAの影響が強いので割合を下げる。
inswapper付のfaceswapを使うと効率アップ

Dynamic Promptを使えばOK
メモ
1girl, solo, narrow waist, asymmetrical parted bangs,
{ light smile | angry | surprised | sleepy | cry },
{ open mouth | closed mouth }, { open eye | closed eye }
{ lookin at viewer | looking back | looking to the side | looking at another | looking away },
detailed face, 
{ completely nude , pubic hair, | decorated light green lingerie }, 
{ from above | from below | full frontal },
changing room, laundry, shelf, towel, mirror, tooth brush, cup,
best anatomy, best quality, absurdres, medium hair, 
{ standing | squatting leaning forward | leaning back | leaning to the side | lying},
{ arms behind back | arms up | hand up | spread legs | legs up } 
<lora:hiyamasaya_lora-05:0.8> 

# 画像作成のコツ
手法1 LoRAで学習させて画像を出す。出した画像に対して、insightfaceとcodeformerで仕上げる
手法2 LoRAなしで画像を出してADetailerで全体にLoRAを適用する。（epic系だと白人っぽさが強く出る）
手法3 適当に拾った画像にADetailerをしたあとにinsightfaceとcodeformer。（元画像に左右されにくい



# LoRA作成のコツ
* 人物系
  * 人物系は顔だけ学習させたほうが良い。
  * 画質は基本的に高いほど良い。画質が悪いとタグ付けの精度が悪くなる。
  * 高画質化した画像2枚
    * epoch16 雰囲気は似てる
    * epoch25 おしい
    * epoch30 OK?
    * epoch50 OK?
    * epoch80 OK?
    * epoch100 上半身のみになる
    * epoch300 元画像のみ。画質荒れる。
  * CivitaiのTrainとの比較
    * civitaiではepoch16でも荒れていたが、解消した。タグ付けが重要？
    * epoch30~50が良さげ。
    * 学習する画像のパターンのバリエーションが少ないと16くらいで収束して学習が終わる感じ
  * 過学習気味だとハイライトがきつくなってくる模様。コントラストが強くなる元画像の構図しかでなくなる。 
  * 要検証
    * 顔の角度、バリエーションが多い場合はepochは少なめのほうが良い？多いとザラついた
    * バリエーションが少ない場合は、epoch数多めのほうが良い？　多いと精度上がった
* 枚数が多いほうが良い。できれば40枚程度。足りない場合は左右反転画像などを入れる
* epoch数は多いほうが良い。ただし枚数が40枚程度あれば16程度でもOK.　
* 基本的に画質高いほうが良い。
* 画質が悪い場合はepochが低いほうがザラツカナイ？
* 
* 余計なアノテーションがあるくらいなら、anotationなしで学習させたほうがよい？
* リアル系のcheckpointの場合、学習が足りないと画像が荒れる。(checkpointによる）

