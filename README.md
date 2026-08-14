# vimium-config

Vimiumの設定ファイルです.

## 設定内容

- Link Hintsで使う文字を`fdsaqwertgvcxz`に限定.
- Link Hintsを水色に変更.
- Link Hintsの文字サイズを18pxに拡大.

## Import

VimiumのOptionsを開き, `Backup and Restore`から`vimium-options.json`をimportします.

## Troubleshooting

### Microsoft EdgeのGoogle検索結果でVimiumが動かない

`example.com`などではVimiumが動くのに, Google検索結果では`f`や`?`が反応しない場合は, Edgeのpolicyを確認します.

Vimiumのpopupに`All Vimium keys are enabled on this page.`と表示され, 拡張機能の`サイト アクセス`も`すべてのサイト`になっている場合でも, EdgeのpolicyによってVimiumのscript注入がhost単位でblockされていることがあります.

1. `edge://policy`を開きます.
2. `ExtensionSettings`を確認します.
3. `runtime_blocked_hosts`でGoogleを含む対象hostがblockされていないか確認します.
4. blockされている場合は, policyの設定元で該当hostのblockを解除します.
5. EdgeとGoogle検索結果ページをreloadして, `f`または`?`が動くことを確認します.

組織管理されたEdgeでは, 拡張機能側の設定だけではなく, `ExtensionSettings`の`runtime_blocked_hosts`も確認する必要があります.
