# BASE-01 UX 2.0 の全体像（Configuration Group と Feature Profile）

- 時間: 10 分 / 前提: なし / 使う画面: SD-WAN Manager

## 目的

SD-WAN Manager の UX 2.0 では、機器の設定を Configuration Group と、その部品の Feature Profile で組み立てます。
大規模拠点（site-74）の Configuration Group `SHOW-LARGE` を開き、中身を順に見ます。

## 流れ

| 手順 | やること | 確認すること | 確認 |
|---|---|---|---|
| 1 一覧を開く | **Configuration** > **Configuration Groups** を開き、`SHOW-LARGE` を探す | 機器が 2 台付いている | 自己申告 |
| 2 Feature Profile | `SHOW-LARGE` を開き、System、Transport & Management、Service、CLI Add-On の 4 つを見る。System と Transport を開いて中身を見る | 4 つの Profile がある | クイズ（WAN 側の設定はどの Profile か） |
| 3 サービス側の VPN | Service Profile（`SHOW-LARGE_CPOC-DEMO-Single-Router_LAN`）を開き、VPN と LAN のインタフェースを見る | サービス側の VPN がある | クイズ（どの VPN が入っているか） |
| 4 付いている機器 | **Associated Devices** を開く | C8475-G2-1（7.4.4.1）、C8475-G2-2（7.4.4.2）、site-74 | クイズ（2 台が同じグループを使える理由） |
| 5 読み取り専用 | Feature Profile を 1 つ開き、編集・保存・デプロイのボタンを探す（押さない） | 保存もデプロイもできない | 自己申告 |

## 補足

- site-74 の物理のルータはいま保留中で、到達できない状態のことがあります。このツアーで見るのは設定の中身なので、進め方は変わりません
- LAN のアドレスは `10.<site-id>.<VPN 番号>.0/24`（例: site-74 の CORP は 10.74.10.0/24）
