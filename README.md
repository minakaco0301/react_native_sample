# アジェンダ
0.
1.
2.
3.
4.
5. Flexbox Layoout
6. ライブラリ
7. 実機ビルド
8. iOS申請
9. 参考資料

#0.ReactNativeのメリットデメリット
・Reactを用いてiOSやAndroidのネイティブアプリを構築できるフレームワーク<br>
・JavaScriptからネイティブのAPIが呼ばれる<br>
・一度覚えればどのプラットフォーム向けにも書けるようになる<br>

###メリット
- ネイティブアプリがJavaScriptで書ける<br>
- アプリを素早くビルドできる<br>
- CSSのサブセットがあるため、CSSでスタイリングできる<br>

###デメリット
- ロジックはJavaScriptのため、重い処理が苦手<br>
- 複雑なUIになると、ネイティブコードを書かざるを得なくなる<br>

###デバッグ
⌘+Dでメニュー画面表示(iosの場合)

- Debug JS Remotely - デベロッパーツールの機能が利用できる<br>
- Enable Live Reload - 保存のたびにリロードが走る（初期画面に戻る）<br>
- Enable Hot Reloading - 保存時に現在表示してる画面のままリロードが走る<br>
- Show Inspector - アプリのレイアウト確認ができる<br>
- Show Perf Monitor - パフォーマンスの確認ができる<br>


#1.Reactの概要




#2. プロジェクト作成

```
brew install node
brew install watchman
npm i -g react-native-cli
react-native init test && cd test
react-native run-ios

```

#3. 
Link (https://github.com/besutome/slides/tree/master/20161016-ReactNative-handson)

#4. 
#5. Flexbox Layoout 
```
render() {
  return (
    <View style={{flex: 1}}>
      <View style={{flex: 1, backgroundColor: 'powderblue'}} /> 
      <View style={{flex: 2, backgroundColor: 'skyblue'}} />
      <View style={{flex: 3, flexDirection: 'row'}} >
        <View style={{width: 30, backgroundColor: 'darksalmon'}} /> 
        <View style={{flex: 1, backgroundColor: 'lightsalmon'}} /> 
        <View style={{width: 100, backgroundColor: 'peachpuff'}} />
      </View> 
    </View>
  );
}
```

flexDirectionではflexboxで要素を並べる方向を定めることができます。
デフォルトの縦方向がcolumn、横方向がrowです。
要素を固定長で指定することもできます。width: 40など。
他にも様々な関連プロパティがあり、柔軟にレイアウトすることができます。
cssとの違いはいくつかありますが、重要なのはz-indexを指定できないことです。
重ね順を変更するにはコンポーネントの順序を変えることで対応します。


#6. ライブラリ
Link: ()

#7. 実機ビルド

#8. iOS申請

#9. 参考資料
Link1: (https://github.com/besutome/slides/tree/master/20161016-ReactNative-handson)
Link2: (https://github.com/besutome/slides/tree/master/20160918-react-handson)

