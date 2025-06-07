- 環境構築をしっかりしよう by 寺田さん
- 環境構築ができると成長が早い
- fastapiはバックエンドに特化している
- ローカルホストに飛んだあと、`http://127.0.0.1:8000` のあとに`http://127.0.0.1:8000/docs`とやるとAPI referenceが出てくる
- 良い点：エラーメッセージをちゃんと出しやすい
- `uvicorn main:app --reload` でmain.pyの変更を勝手に反映させてreloadしてくれる
- python では型ヒントをなるべくつけよう
- 最近だと型ヒントを書くようになったのでdocstringを書かなくてもいいんじゃないかという議論があるらしい
- `uv run ruff check` で勝手にスペースが空いたり反映できる
- [ruff](https://docs.astral.sh/ruff/)が最近がデファクトになってきているらしい
- [Pydantic](https://docs.pydantic.dev/latest/)というツールがあるらしい
- [Enum型について](https://fastapi.tiangolo.com/ja/tutorial/path-params/#enum)
- [おすすめ：エキスパートPythonプログラミング 改訂4版](https://www.kadokawa.co.jp/product/302304004673/)
- https://fastapi.tiangolo.com/tutorial/query-params/?h=optional+para#optional-parameters
- pythonにおいてはbool関数は、0はfalseになる
- bool型のTrue はint型の`1`らしい
- `...` は elipsisと呼ぶらしい
- https://gist.github.com/promto-c/f51cc2c0eb8742ce5cc3e65601df2deb
- 循環参照を防ぐためにはimportの順番で解消できるが、現在importの並べ方にうるさいのでそのハックがあまりできないため、`main.py`に全て書かずにファイルを分割したようだ
- `searchapi.py`の中にある複数のモデルを非同期で投げることができる `複数の問い合わせを非同期に実行する `agrid_query_gemini` 関数`があるらしい
- 非同期だと一気にバッとできるらしい
- `uv run ruff check --fix`
- これでフロントエンドをstremlitなどで作る
- 

&nbsp;

&nbsp;

## 実行の仕方

```bash
$ uv init -p python3.13
$ uv add "fastapi[all]"
$ uv add "langchain-google-genai"
$ uv add --optional dev ruff pyright pytest pytest-asyncio httpx
uv sync --extra 'dev'
```

これでlocal host に飛び、`/docs`をつけるとreferenceが開ける
