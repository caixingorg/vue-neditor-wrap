# vue-neditor-wrap 数据绑定失败修复版本

> A editor component development based on vue-neditor-wrap [@caiya](https://github.com/caiya/vue-neditor-wrap))

> 主要修复 部分时候绑定数据失败的情况  主要原因是在 loadscript 回调变成两次 _initEditor   value  值丢失 所以在 _beforeInitEditor 把 readyValue 统一初始化 传到  _initEditor 进行数据绑定

## Installation
```bash
$ git cone https://github.com/lyw90/vue-neditor-wrap
```

## Quick Start

1. 下载[官方资源文件](https://www.notadd.com/download/neditor/Neditor-next-master.tar.xz)

    > 下载完成后放在本地public下，命名为NEditor的文件夹下

2. 引入`VueNeditorWrap`组件

    `import VueNeditorWrap from 'vue-neditor-wrap'`

3. 注册组件
    ```js
    components: {
        VueNeditorWrap
    },
    ```
4. `v-model`绑定数据
    ```html
    <vue-neditor-wrap v-model="content" :config="myConfig" :destroy="false" @ready="ready"></vue-neditor-wrap>
    ```
    ```js
    data () {
        return {
            myConfig: {
                // 如果需要上传功能,找后端小伙伴要服务器接口地址
                serverUrl: '/api/web/upload/ueditor',
                // 你的UEditor资源存放的路径,相对于打包后的index.html
                UEDITOR_HOME_URL: '/NEditor/',
                // 编辑器不自动被内容撑高
                autoHeightEnabled: false,
                // 初始容器高度
                initialFrameHeight: 240,
                // 初始容器宽度
                initialFrameWidth: '100%',
                // 关闭自动保存
                enableAutoSave: false
            },
            content: '',
        }
    }
    ```
## License

[MIT](http://opensource.org/licenses/MIT)

