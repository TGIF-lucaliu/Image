# MXFlutter

[English Document](https://www.baidu.com)

MXFlutter是一套基于JS的高性能Flutter动态化框架，它用极类似Dart的开发方式，通过编写JavaScript代码，来开发Flutter应用。更多细节在[这里](https://juejin.im/post/5d11a4f06fb9a07ec63b21ea)。

## 特性

* 支持Dart Flutter语法
* 支持定义Flutter中同名Widget类
* 支持定义相同的Build方式，SetState刷新及事件响应方法
* 支持js模块化开发
* 支持VS Code直接调试
* 支持模拟器页面热更新

## 示例代码

```
class HomePage extends MXJSWidget {
    constructor(){
        super("HomePage", {key: "HomePage"});
    }

    barSearch(){
        return new Container({
            child: new Row({
                children: [
                    new Expanded({
                        child: FlatButton.icon({
                            onPressed:function(){
                                this.navigatorPush(new SearchPage);
                            },
                            icon: new Icon(new IconData(0xe8b6, {fontFamily: 'MaterialIcons'}),{
                                color: GlobalConfig.fontColor,
                                size: 16.0,
                            }),
                            label: new Text("坚果R1摄像头损坏",{
                                style: new TextStyle({
                                    color: GlobalConfig.fontColor,
                                }),
                            }),
                        }),
                    }),
                    new Container({
                        decoration: new BoxDecoration({
                            border: new BorderDirectional({
                                start: new BorderSide({
                                    color: GlobalConfig.fontColor,
                                    width: 1.0,
                                },)
                            }),
                        }),
                        height: 14.0,
                        width: 1.0,
                    }),
                    new Container({
                        child: FlatButton.icon({
                            onPressed: function(){
                                this.navigatorPush(new AskPage);
                            },
                            icon: new Icon(new IconData(0xe22b, {fontFamily: 'MaterialIcons'}),{
                                color: GlobalConfig.fontColor,
                                size: 16.0,
                            }),
                            label: new Text("提问", {
                                style: new TextStyle({
                                    color: GlobalConfig.fontColor,
                                }),
                            }),
                        }),
                    }),
                ],
            }),
            decoration: new BoxDecoration({
                borderRadius: BorderRadius.all(Radius.circular(4.0)),
                color: GlobalConfig.searchBackgroundColor,
            }),
        })
    }

    build(context){
        let widget = new DefaultTabController({
            length: 3,
            child: new Scaffold({
                appBar: new AppBar({
                    title: this.barSearch(),
                    bottom: new TabBar({
                      labelColor: Colors.blue(),
                      indicatorColor: Colors.blue(),
                      unselectedLabelColor: Colors.black(),
                      tabs: [
                        new Tab({text: "关注"}),
                        new Tab({text: "推荐"}),
                        new Tab({text: "热榜"}),
                      ],
                    }),
                    backgroundColor: Colors.white(),
                }),
                body: new TabBarView({
                    children: [
                        new Follow(),
                        new Recommend(),
                        new Hot(),
                    ]
                }),
            }),
        });
        return widget;
    }
}
``` 

## 效果

![](https://github.com/langbluesky/Image/blob/master/demo.gif?raw=true)
在此，鸣谢Flutter版作者[HackSoul](https://github.com/HackSoul)，笔者从这里[zhihu-flutter](https://github.com/HackSoul/zhihu-flutter)借鉴的示例代码。

## 如何开始



## 许可协议

MXFlutter遵循MIT开源许可证协议。

## QQ群

对MXFlutter感兴趣的小伙伴，可以加QQ群交流，QQ群: 747535761
![qrcode](https://github.com/langbluesky/Image/blob/master/qrcode.png?raw=true)



