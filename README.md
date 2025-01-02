# tampermonkey-remove-baidu-ads

Tampermonkey script for removing Baidu ads

## 功能

1. 去除百度首页搜索框自动加载的热搜内容词条，清空搜索框中的 placeholder 的元素
2. 去除百度首页搜索框下的 “即刻体验百度AI搜”

## 教程

### 1. 安装 Tampermonkey 插件
首先，确保你已经安装了 Tampermonkey 插件，Tampermonkey 是一个在浏览器中运行用户脚本的扩展。

- **Chrome**: 访问 [Chrome 网上应用店](https://chrome.google.com/webstore/detail/tampermonkey) 安装 Tampermonkey。
- **Firefox**: 访问 [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/) 安装 Tampermonkey。

### 2. 创建 Tampermonkey 脚本
接下来，你可以在 Tampermonkey 中创建一个新的用户脚本。

1. **打开 Tampermonkey** 扩展，点击浏览器工具栏上的 Tampermonkey 图标。
2. 选择 **“创建新脚本...”**。
3. 删除默认的模板代码，替换为以下脚本。

```javascript
// ==UserScript==
// @name         屏蔽百度搜索页面的引导
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  屏蔽百度搜索页面中的 id="s_new_search_guide" 的 div 元素
// @author       你
// @match        https://www.baidu.com/*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // 等待页面加载完成
    window.addEventListener('load', function() {
        var targetElement = document.getElementById('s_new_search_guide');
        if (targetElement) {
            targetElement.style.display = 'none';  // 隐藏元素
        }
    });
})();
```

### 3. 代码解释
- `@name`：插件的名字，随便设置一个名称，例如 "屏蔽百度搜索页面的引导"。
- `@namespace`：用户脚本的命名空间，通常用 Tampermonkey 提供的默认值即可。
- `@version`：脚本的版本号，可以根据需要调整。
- `@description`：脚本的描述，简单说明脚本的功能。
- `@author`：脚本作者，你可以填上自己的名字。
- `@match`：这个规则表示脚本只在 `https://www.baidu.com/*` 页面上生效，确保只在百度的搜索页面执行。
- `@grant`：指定脚本是否需要特殊权限，在本例中我们不需要额外的权限。

### 4. 保存并测试脚本
1. 保存并启用脚本。
2. 打开百度搜索页面，查看 `id="s_new_search_guide"` 的 `div` 是否被成功屏蔽。

### 5. 上传到 GreasyFork
如果你希望将该脚本上传到 GreasyFork 与他人分享，请按照以下步骤操作：

1. **注册 GreasyFork 账户**: 访问 [GreasyFork](https://greasyfork.org/)，并创建一个账户。
2. **上传脚本**:
   - 在 GreasyFork 网站上点击右上角的 **“提交脚本”** 按钮。
   - 填写脚本的名称、描述等信息，并上传你刚刚编写的脚本。你可以复制上面代码的内容并粘贴到 GreasyFork 的编辑框中。
   - 提交脚本后，它会出现在你的 GreasyFork 个人页面上，其他用户也可以安装。

