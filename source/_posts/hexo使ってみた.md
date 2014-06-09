title: Hexo使ってみた
date: 2013-09-30 04:49:17
categories:
 - 開発
 - node
tags:
 - node
 - hexo
---
# 導入
[geta](https://twitter.com/geta6)さんに影響されて、最近Nodeを始めた。あとブログも始めてみようとも思っていたので、この機会にブログをNodeで作ってみようと考えた。
Nodeのブログエンジンはいくつかあったのだけど、hexo(http://zespia.tw/hexo/ )というblogのflameworkが個人的にシンプルでいい感じだと思ったので、これを導入することにした。
インストールの方法はhttp://zespia.tw/hexo/docs/ に丁寧に書いてある。
Javaと比べて、Nodeはこういうモジュールとかライブラリのインストールが楽で助かる。

さっそく記事を作ってみることにした。
hexoのsetup(方法→http://zespia.tw/hexo/docs/setup.html )後に
{% codeblock %}
$ hexo new "ブログ始めてみた"
# source/_posts/ブログ始めてみた.md が作成される
{% endcodeblock %}
vimで"ブログ始めてみた.md"を編集。
markdown記法というやつで編集するらしい。
{% img http://gyazo.com/71a6e2f2463555eed5ce1184d4c6946d.png %}
こんな感じで編集した。
{% codeblock %}
$ hexo server
{% endcodeblock %}
で起動。アクセスしてみると、
{% img http://gyazo.com/4675cab2753d6ee4ec6a9159f058c11d.png 400 300 %}
あっさり動いた。
※ブログのタイトルは_config.ymlで編集

# 簡単なカスタマイズ
hexoはデフォルトだとコメント機能がない。しかしコメント機能は[disqus](http://disqus.com/)というコメント機能を提供する外部サービスのshortnameを使うと簡単に導入できる。disqusに登録してShortnameを取得、_config.ymlのdisqus_shortnameに取得した値をセットすると動く。

また、ソーシャルボタンは[Add this](http://www.addthis.com/)を使うらしい。
このあたりは自前で用意した方が本当はベストだけど、そこまでのやる気は起きなかった。

RSSも初期実装はされてないので、どうしよう...と思ったらpluginあった
https://github.com/tommy351/hexo-plugins/tree/master/generator/feed

install後に_config.ymlをUsageに書いてある通りに編集。
ただRSSがどのURLで取得できるかわからない。Usageにも書いてない！　困った！

ググってたら中国語のページにそれっぽいこと(http://zipperary.com/2013/06/02/hexo-guide-5/ )が書いてあった。直下の/atom.xmlにあるっぽい。
→あった！

めでたし。めでたし。

# 感想・その他
markdownに慣れていれば、導入も簡単だし使いやすいフレームワークだと思う。
構造がシンプルなのも好み。まだNodeは始めたばかりだし、hexoの機能を完全に理解したわけではないが、カスタマイズも今後行いたい。

そういえば、今までずっとIDE(netbeans)頼みだったので、JS書くときに良いエディタが無くて困っている。
getaさんにオススメされたsublime textでも使ってみるか。


参考: http://www.moongift.jp/2013/06/20130605/
