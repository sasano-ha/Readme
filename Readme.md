# **SHOOTIG STAR**
## **制作概要**
* 制作時期....2022年11月
* 制作期間....約8ヵ月
* 制作環境....Unity
* 制作人数....1人
* 使用言語....C#
* [GitHub](https://github.com/sasano-ha/GameEngine)
## **作品概要**
* リアリティがあるシューティングゲーム！！
## **操作方法**
* WASD....上下左右移動
* マウスカーソル....照準
* 左クリック長押し.....弾を発射
## **ゲーム概要**
* クリアと言う概念があるゲームではなく、ひたすらスコアを稼ぐゲームとなっています。自機にはHpがあるのでHpが0になるとそこまでのスコアしか稼げません。0になった場合は仕様としてはゲームオーバー扱いになります。
## **エピソード**
* 就職作品を決めるにあたって、何か突出した作品を作らなければいけないと言う固定概念に捕らわれ凝った作品を作ろうとしていたが、自分にできる作品なのかを考え直したところ今の作品を作成。
* ただのシューティングだと面白くないので、他と違いを作るためスピード感や操作性をリアリティーがあるように意識した。
* 今回はUnityを使っています。Unityでしか表現できなかったことをしたかったので使用しました。更に独学で1から学んでいます。
## **特に見てほしいポイント**
* PlayerHpBar.sc  21行目~42行目<br>
  自機のHpBarの処理を行っているところ。ここの処理は自機の影響とHpの見せ方を考えながら改良をした。
  <br>
  <br>
  自機がダメージを受ける。
  <br>
  ↓
  <br>
  fillAmount全体の値からHpを引き、出た差分を100で割る。
  <br>
  ↓
  <br>
  計算された値が全体の何%だったらHpBarの色を変えるようにする。
  <br>
  このように書いたことで視覚的にもわかりやすく自機とHpが連携されるようにすることができた。
  <br>
  <br>
* FlushController.sc  33行目~41行目<br>
  自機がダメージを受けた時の反応処理を行っているところ。ここはHpBarのみだけでなく全体を見てもわかるように改良をした。
  <br>
  <br>
  自機がダメージを受ける。
  <br>
  ↓
  <br>
  受けたらフラグを立てる。
  <br>
  ↓
  <br>
  そのフラグが立っていたら、色を赤くする。
  <br>
  ↓
  <br>
  常に赤くなっているとおかしいので徐々に薄くして最終的には透明にする。
  <br>
  このように書いたことによっていつ自機がダメージを受けたのかがより分かりやすくなるようにできた。
  <br>
  ↓
  <br>
  最近では画面全体が赤くなるのはFPS特有のダメージ表現だと思い、部分的に赤くなるようにリソース画像の変更しました。

* Font.sc   37行目~57行目<br>
  unity既存のボタンを使ってしたがそれだとどうしてもunity感が出てしまいゲーム感がなかったためボタンを透明にし、画面全体を覆うように配置しフォントを点滅させるようにコルーチンを使いゲーム感を演出。
  <br>
  <br>
  フラグが立っていなかったらwhile文を回す。
  <br>
  ↓
  <br>
  コルーチンを使いテキストのアルファ値を徐々に透明にする。
  <br>
  ↓
  <br>
  テキストが透明になったら今度はアルファ値を徐々に不透明にする。
  <br>
  ↓
  <br>
  これの繰り返しをして点滅を演出。