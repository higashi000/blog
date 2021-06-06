---
title: "作っている括弧補完pluginがいい感じになってきた"
date: 2021-05-29T18:50:50+09:00
---

<script async src="//cdn.iframe.ly/embed.js" charset="utf-8"></script>

# 始めに
こんにちは、higashiです。  
以前の記事で紹介したVim/Neovimの括弧補完プラグインがとてもいい感じになったので改めて紹介していきたいと思います。  
以前の記事はこちら  
<div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://zenn.dev/higashi000/articles/d1efa3676ceca46fc357" data-iframely-url="//cdn.iframe.ly/4SvfvMg?card=small"></a></div></div><script async src="//cdn.iframe.ly/embed.js" charset="utf-8"></script>

# dps-kakkonanについて
作成した括弧補完プラグインは[dps-kakkonan](https://github.com/higashi000/dps-kakkonan/)といいます。  
[lexima.vim](https://github.com/cohama/lexima.vim)と[vim-sandwich](https://github.com/machakann/vim-sandwich)をリスペクトしています。  

<div class="iframely-embed"><div class="iframely-responsive" style="padding-bottom: 50%; padding-top: 120px;"><a href="https://github.com/higashi000/dps-kakkonan" data-iframely-url="//cdn.iframe.ly/ychJFoQ"></a></div></div>

# インストール方法
dps-kakkonanでは[denops.vim](https://github.com/vim-denops/denops.vim)を利用しているため、denoのインストールが必要となります。  
以下のページを参考にインストールしてください。  
<div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://deno.land/" data-iframely-url="//cdn.iframe.ly/kjlpjoT"></a></div></div>

次に使用しているプラグインマネージャーで以下の2つのプラグインをインストールしてください。  

- [vim-denops/denops.vim](https://github.com/vim-denops/denops.vim)
- [higashi000/dps-kakkonan](https://github.com/higashi000/dps-kakkonan)

例
```
" dein.vim
call dein#add('vim-denops/denops.vim')
call dein#add('higashi000/dps-kakkonan')
```



# 機能
## 括弧補完
普通の括弧補完です。
[![Image from Gyazo](https://i.gyazo.com/977511c3215785e40f41329fdabb5bb4.gif)](https://gyazo.com/977511c3215785e40f41329fdabb5bb4)

### visual modeで選択した範囲を括弧で囲む
囲えます。  
プラグイン側で`<Plug>`を提供しているので設定すれば使えます。  

keymap例
```
" dps-kakkonan surround text to backets example keymap
vmap sr( <Plug>(dps_kakkonan_surround_parenthesis)
vmap sr{ <Plug>(dps_kakkonan_surround_curly)
vmap sr[ <Plug>(dps_kakkonan_surround_square)
vmap sr" <Plug>(dps_kakkonan_surround_doublequote)
vmap sr' <Plug>(dps_kakkonan_surround_singlequote)
vmap sr` <Plug>(dps_kakkonan_surround_backquote)
```

[![Image from Gyazo](https://i.gyazo.com/642cdff83f7767d16b35af9a208a751b.gif)](https://gyazo.com/642cdff83f7767d16b35af9a208a751b)

## 囲っている括弧の削除
消せます。  
消したい括弧の上で以下のコマンドを実行すると消えてくれます。  
```
:KakkonanDelete
```
[![Image from Gyazo](https://i.gyazo.com/4becea036dd2a037193cda74f3303203.gif)](https://gyazo.com/4becea036dd2a037193cda74f3303203)


## 括弧の置き換え
置き換えられます。  
指定した括弧とその閉じ括弧を好きな括弧に置き換えられます。  
こちらも囲む機能と同様に`<Plug>`を提供しているので設定することで使うことができます。  

keymap例
```
" dps-kakkonan replace brackets example keymap
map rp( <Plug>(dps_kakkonan_replace_parenthesis)
map rp{ <Plug>(dps_kakkonan_replace_curly)
map rp[ <Plug>(dps_kakkonan_replace_square)
map rp" <Plug>(dps_kakkonan_replace_doublequote)
map rp' <Plug>(dps_kakkonan_replace_singlequote)
map rp` <Plug>(dps_kakkonan_replace_backquote)
```

[![Image from Gyazo](https://i.gyazo.com/9788368e06d751f4adc0b50958eec300.gif)](https://gyazo.com/9788368e06d751f4adc0b50958eec300)

# 最後に
現在markdownファイルを編集中に上手く動かないバグが発生していますが、こういったバグも直しつつどんどん使いやすくしていきたいと思います。  
