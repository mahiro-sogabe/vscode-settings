# python

## 前提

1. 本ディレクトリの設定はVSCodeの拡張機能([autoDocstring - Python Docstring Generator](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring), [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance), [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python), [Python Debugger](https://marketplace.visualstudio.com/items?itemName=ms-python.debugpy), [ruff](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff))を使用します。

1. ruffの設定に`pyproject.toml`を使用します。

1. docstringのスタイルはnumpyを使用します。

## 使用方法

1. [ruff - PyPI](https://pypi.org/project/ruff/)をインストールする。


1. 以下のコードブロックを適用先のプロジェクトの`pyproject.toml`にコピーする。

```toml
[tool.ruff]
exclude = [
    # 監視対象外のディレクトリまたはファイルパスを記載する
]
indent-width = 4
line-length = 99
target-version = "" # プロジェクトで使用するPythonバージョンを記載する。(例: py312)

[tool.ruff.lint]
ignore = [
    "COM812", # 他のフォーマッタと競合するためignore推奨
    "D100", # モジュール用docstring不要化
    "D203", # D211と互換なしのためignore推奨
    "D213", # D212と互換なしのためignore推奨
    "D400", # docstringの文末に"."不要化
    "D415", # docstringの文末に"./!/?"不要化
    "FIX002", # ToDO記述の代わりにIssue使用の推奨を無効化
    "INP001", # __init__.py不要化
    "ISC001", # 他のフォーマッタと競合するためignore推奨
    "RUF001", # ASCIIに類似したUnicode検知を無効化
    "RUF002", # ASCIIに類似したUnicode検知を無効化
    "S101", # ユニットテストで`assert`を使用するため無効化
    "TD002", # ToDO記述時に記述者名を不要化
    "TD003", # ToDO記述時にIssueの紐づけ不要化
]
select = ["ALL"]

[tool.ruff.lint.pydocstyle]
convention = "numpy"

[tool.ruff.format]
indent-style = "space"
quote-style = "double"
```