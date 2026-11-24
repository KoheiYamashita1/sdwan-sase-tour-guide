# BASE-04 NWPI による通信の可視化

- 時間: 15 分 / 前提: BASE-02 / 使う画面: SD-WAN Manager

## 目的

NWPI（Network-Wide Path Insight）は、拠点の端末の通信がどの機器と回線を通ったかを追う機能です。
管理者が始めておいた 2 つのトレースで、拠点どうしの通信とインターネット向けの通信を見比べます。

## 流れ

| 手順 | やること | 確認すること | 確認 |
|---|---|---|---|
| 1 トレースの一覧 | **Tools** > **Network-Wide Path Insights** を開き、**Traces & Tasks** を押す | `BASE-04-site171` と `BASE-04-site172` が running で、View Insights がある | 自己申告 |
| 2 追える通信 | 説明を読む（NWPI の制限） | — | クイズ（追えるプロトコル） |
| 3 拠点どうし | `BASE-04-site171` の View Insights。10.171.10.100 から 10.172.10.101 の 3389 の通信の View を押す | Path Visualization で端末、C8KV-171、C8KV-172、席がつながり、間に BIZ_INTERNET | 自己申告 |
| 4 ホップの表 | Flow readout の Overview と Routing Insight を見る | — | クイズ（Local Color の意味） |
| 5 インターネット向け | `BASE-04-site172` の View Insights。宛先 443（www.cisco.com）の通信の View を押す | Routing Insight で Path Decided By が data policy、Final Path が SSE TUNNEL | 自己申告 |
| 6 アプリの見分け | Applications のタブと説明を読む | — | クイズ（App Visibility を有効にすると何が起きるか） |

## 補足

- **New Trace、Stop、Delete は押さないでください。** トレースは機器ごとに同時に 2 つまでで、ほかの体験者のトレースが止まります
- トレースは体験会の時間に合わせて管理者が始めます。一覧に 2 つが無いときは、会場の担当者に知らせます。担当者がいないときは、ポータルの説明と表を読んで進めます
- 手順 5 の結果は SSE-01（SIA）の仕組みそのものです。先に見ておくと SSE-01 が分かりやすくなります
