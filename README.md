# Portfolio

Vite + Vue 3 + TypeScript で構成した静的ポートフォリオです。

## 開発

```sh
bun install
bun run dev
```

## 検証・ビルド

```sh
bun run check
bun run build
```

依存関係の新規解決では、`bunfig.toml` により公開から48時間未満のバージョンを除外します。さらに Socket の Bun Security Scanner がインストール前に依存パッケージを検査します。
