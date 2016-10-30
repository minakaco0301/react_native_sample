# アジェンダ

0. ReactNativeのメリットデメリットとデバック<br>
1. プロジェクト作成<br>
2. Reactの概要<br>
3. <br>
4. Flexbox Layoout<br>
5. ScrollViewとListView<br>
6. ライブラリ<br>
7. 実機ビルド<br>
8. iOS申請<br>
9. 参考資料<br>

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



#1. プロジェクト作成

```
brew install node
brew install watchman
npm i -g react-native-cli
react-native init test && cd test
react-native run-ios

```

#2.Reactの概要

2つのデータをコントールする為のコンポーネントがあります。propsとstateです。
- 
- 




###
Most components can be customized when they are created, with different parameters. These creation parameters are called props.
For example, one basic React Native component is the Image. When you create an image, you can use a prop named source to control what image it shows.
Link (https://facebook.github.io/react-native/docs/props.html#content)

 
#3. Flexbox Layoout 
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

flexDirectionではflexboxで要素を並べる方向を定めることができます。<br>
デフォルトの縦方向がcolumn、横方向がrowです。<br>
要素を固定長で指定することもできます。width: 40など。<br>
他にも様々な関連プロパティがあり、柔軟にレイアウトすることができます。<br>
cssとの違いはいくつかありますが、重要なのはz-indexを指定できないことです。<br>
重ね順を変更するにはコンポーネントの順序を変えることで対応します。<br>

#4. ScrollViewとListView


#5. ルーティング


#6. ライブラリ
React Native向けのライブラリはnpmで提供されています。 <br>
ほとんどがnpm installで利用できますが、ものによっては設定ファイルを編集する必要があります。<br>
Link: ( https://react.parts/native )

#7. 実機ビルド

#8. iOS申請

#9. 参考資料
Link1: (https://github.com/besutome/slides/tree/master/20161016-ReactNative-handson)
Link2: (https://github.com/besutome/slides/tree/master/20160918-react-handson)

