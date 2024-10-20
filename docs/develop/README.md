#### 开发环境
---

##### 打造vscode编辑器

推荐插件：   
- `Excalidraw` 画图工具   
- `gitlens` git管理工具 

字体推荐:
- [geist mono font](https://befonts.com/geist-mono-font-family.html) - 高颜值的字体   

主题推荐:
- [Aura Theme](https://marketplace.visualstudio.com/items?itemName=DaltonMenezes.aura-theme)

快捷键推荐：
- 安装插件:
    - Emacs, multi-command
- 修改keybindings.json：
```json
[
    // 光标移动
    // C+n C+p C+f C+b
    // C+alt+n C+alt+p C+alt+f C+alt+b
    // C+e C+m
    // C+alt+l 
    {
        "key": "ctrl+alt+o",
        "command": "editor.action.organizeImports"
    },
    {
        "key": "alt+1",
        "command": "workbench.action.focusFirstEditorGroup"
    },
    {
        "key": "alt+2",
        "command": "workbench.action.focusSecondEditorGroup"
    },
    {
        "key": "ctrl+alt+\\",
        "command": "workbench.action.gotoLine",
        "when": "textInputFocus"
    },
    {
        "key": "ctrl+e",
        "when": "textInputFocus",
        "command": "emacs.cursorEnd"
    },
    {
        "key": "ctrl+m",
        "command": "emacs.cursorHome",
        "when": "textInputFocus"
    },
    {   
        "key": "ctrl+f", // 右移一个字符
        "command": "emacs.cursorRight",
        "when": "textInputFocus"
    },
    {
        "key": "ctrl+alt+f", // 右移一个word
        "command": "emacs.cursorWordRight",
        "when": "textInputFocus"
    },
    {   
        "key": "ctrl+b", // 左移一个字符
        "command": "emacs.cursorLeft",
        "when": "textInputFocus"
    },
    {
        "key": "ctrl+alt+b", // 左移一个word
        "command": "emacs.cursorWordLeft",
        "when": "textInputFocus"
    },
    {  
        "key": "ctrl+alt+n", // 向下多行
        "command": "extension.multiCommand.execute",
        "args": {
            "sequence": [
                "emacs.cursorDown",
                "emacs.cursorDown",
                "emacs.cursorDown",
                "emacs.cursorDown",
                "emacs.cursorDown",
            ]
        },
    },
    {  
        "key": "ctrl+alt+p", // 向上多行
        "command": "extension.multiCommand.execute",
        "args": {
            "sequence": [
                "emacs.cursorUp",
                "emacs.cursorUp",
                "emacs.cursorUp",
                "emacs.cursorUp",
                "emacs.cursorUp",
            ]
        },
        "when": "textInputFocus"
    },
    // 回到上一步，取消回到上一步
    {
        "key": "ctrl+[",
        "command": "undo",
    },
    {
        "key": "ctrl+]",
        "command": "redo"
    },
    // 插入一行
    {
        "key": "ctrl+o",
        "command": "extension.multiCommand.execute",
        "args": {
            "sequence": [
                "emacs.cursorUp",
                "emacs.cursorEnd",
                "editor.action.insertLineAfter"
            ]
        }
    },
    // 删除当前行
    {
        "key": "ctrl+k",
        "command": "extension.multiCommand.execute",
        "args": {
            "sequence": [
                "cursorLineStart",
                "emacs.C-k"
            ]
        }
    },
    // 复制select 区域
    {
        "key": "ctrl+space",
        "command": "emacs.enterMarkMode",
        "when": "textInputFocus"
    },
    {
        "key": "alt+w",
        "command": "editor.action.clipboardCopyAction",
        "when": "textInputFocus"
    },
    {
        "key": "ctrl+y",
        "command": "editor.action.clipboardPasteAction",
        "when": "textInputFocus",
    },

    // 控制侧边栏
    {
        "key": "ctrl+w ctrl+o",
        "command": "workbench.action.toggleSidebarVisibility",
    },
    {
        "key": "ctrl+w ctrl+p",
        "command": "workbench.action.previousSideBarView"
    },
    {
        "key": "ctrl+w ctrl+n",
        "command": "workbench.action.nextSideBarView"
    },
    // 全文搜索
    {
        "key": "ctrl+w ctrl+;",
        "command": "workbench.action.terminal.searchWorkspace"
    },
    // 全文搜索文件
    {
        "key": "ctrl+w ctrl+f",
        "command": "workbench.action.quickOpen"
    },
    // 触发建议
    {
        "key": "ctrl+alt+i",
        "command": "editor.action.triggerSuggest"
    },
    // 下一条搜索结果
    {
        "key": "ctrl+w ctrl+.",
        "command": "search.action.focusNextSearchResult",
        "when": "hasSearchResult || inSearchEditor"
    },
    {
        "key": "f4",
        "command": "-search.action.focusNextSearchResult",
        "when": "hasSearchResult || inSearchEditor"
    },
    {
        "key": "ctrl+w ctrl+,",
        "command": "search.action.focusPreviousSearchResult",
        "when": "hasSearchResult || inSearchEditor"
    },
    {
        "key": "shift+f4",
        "command": "-search.action.focusPreviousSearchResult",
        "when": "hasSearchResult || inSearchEditor"
    },
    // 转到定义
    {
        "key": "ctrl+enter",
        "command": "editor.action.revealDefinition"
    },
    // 转到跳转前
    {
        "key": "ctrl+-",
        "command": "workbench.action.navigateBack"
    }
]
```

