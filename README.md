http://react-native-meetup.connpass.com/event/39685/

# アジェンダ

0. ReactNativeのメリットデメリットとデバック<br>
1. プロジェクト作成<br>
2. Reactの概要<br>
3. Flexbox Layoout<br>
4. ScrollViewとListView<br>
5. ライブラリ<br>
6. 実機ビルド<br>
7. iOS申請<br>
8. 参考資料<br>

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

Reactは Component というモジュールを使い、複数のComponentを組み合わせて実装します。
```


```

コンポーネントがもつ値には、データをコントールする為にpropsとstateがあります。

- Props<br>

Most components can be customized when they are created, with different parameters. These creation parameters are called props.
例えば, １つの基本的なReact NativeのコンポーネントはImageです。
画像を表示するのを制御したいときは、sorceという名前のpropを使います。
Link (https://facebook.github.io/react-native/docs/props.html#content)
- State<br>
Propsは一度コンポーネントが作成されると変更されませんが、 Stateはコンポーネントの中で変更される値を保持するために使います。

```
class Text extends Component {
   constructor(props) {
     super(props);
     this.state = {
       showText: true
     };

     setInterval(() => {
      this.setState({
        showText: !this.state.showText
      });
     }, 1000);
   }

  render() {
    const text = this.state.showText? this.props.text : '';
    return (
      <div>
        <span style={{color: "red"}}>
          {text}
        </span>
      </div>
    );
  }
}

```




 
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


![Flexbox Layoout](http://i.imgur.com/Lup038j.png "Flexbox Layoout " style" width:400px")

#4. ScrollViewとListView

```
      <ScrollView>
        <View style={{height: 400, backgroundColor: 'powderblue'}} >
          <Text style={{fontSize: 100}}>hoge</Text>
        </View>
        <View style={{height: 400, backgroundColor: 'skyblue'}} >
          <Text style={{fontSize: 100}}>fuga</Text>
        </View>
        <View style={{height: 400, backgroundColor: 'deepskyblue'}} >
          <Text style={{fontSize: 100}}>foo</Text>
        </View>
        <View style={{height: 400, backgroundColor: 'dodgerblue'}} >
          <Text style={{fontSize: 100}}>bar</Text>
        </View>
      </ScrollView>
```
※ Listviewまだ試せてない

#5. ルーティング
```
import React, { Component, PropTypes } from 'react';
import { AppRegistry, Navigator, Text, TouchableHighlight, View } from'react-native';

class MyScene extends Component{
  static propTypes = {
    title: PropTypes.string.isRequired
  };
  render() {
    return (
      <View style={{padding: 30}}>
        <Text>タイトル:{this.props.title}</Text>
      </View>
    );
  }
}

class AwesomeProject extends Component {
  render() {
    return (
      <Navigator
        initialRoute={{title: 'MyInitialScene', index: 0}}
        renderScene={ (route,navigator) =>
          <MyScene title={route.title}/>
        }
      />
    )
  }
}

AppRegistry.registerComponent('AwesomeProject',()=>AwesomeProject);
```


#6. ライブラリ
React Native向けのライブラリはnpmで提供されています。 <br>
ほとんどがnpm installで利用できますが、ものによっては設定ファイルを編集する必要があります。<br>
Link: ( https://react.parts/native )

#7. ReactNarive上のSyntax
Links1: ( http://facebook.github.io/react-native/docs/javascript-environment.html#javascript-syntax-transformers )
Links1: ( http://lealog.hateblo.jp/entry/2016/05/29/233244 )

#8. シュミレーターで実機ビルド確認
test/ios/test.xcodeprojにプロジェクトファイルがあります。
xcodeを開いて、再生マークをクリックします。

#9. iOS申請

Link1: (http://examination-03.hatenablog.com/)
... (to be continued)


#10. 参考資料
Link1: (https://github.com/besutome/slides/tree/master/20161016-ReactNative-handson)<br>
Link2: (https://github.com/besutome/slides/tree/master/20160918-react-handson)<br>
Link3: (http://yutamasun.sakura.ne.jp/blog/2016/03/21/react-native-01/)

