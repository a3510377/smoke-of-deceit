# `.gitattributes` 應用

### 檔案渲染

Github 渲染檔案時會先根據 `.gitattributes` 中的 `linguist-language` 在根據副檔名進行渲染。

```gitattributes
*.py linguist-language=Markdown
```

如果創建該如上檔案，`*.py` 將會使用 Markdown 的渲染方式進行渲染。[test.py](./test.py)
同時語言統計也會將 `*.py` 併入 `Markdown` 的統計中。

### 隱藏 `Languages` ( 關閉語言統計 )

如果你想隱藏特定程式語言( 不讓它顯示在 github languages 中 )

![github-show-languages](./.github/github-show-languages.jpg)

可以將在 `.gitattributes` 添加以下規則

```gitattributes
*.js linguist-documentation
```

你會發現過一段時間後你的 `Repo-Languages` 中沒有了 `JavaScript` ( 就和當前的 儲存庫一樣 )

如果你要對部分的文件使用可以使用以下規則

```gitattributes
test/*.py linguist-vendored
```

其他可用規則:

| Git attribute                                        | Effect on file                                 |
| :--------------------------------------------------- | :--------------------------------------------- |
| `linguist-detectable`=&lt;<u>*type: bool*</u>&gt;    | 包含在統計中，即使語言類型是 `data` 或 `prose` |
| `linguist-documentation`=&lt;<u>*type: bool*</u>&gt; | 從統計中移除                                   |
| `linguist-vendored`=&lt;<u>*type: bool*</u>&gt;      | 從統計中移除                                   |
| `linguist-generated`=&lt;<u>*type: bool*</u>&gt;     | 從統計中移除隱藏在差異                         |

### 參考文章

1. [github-linguist](https://github.com/github/linguist)
