# SSE-01 CORP の通信を SD-WAN から CSA へ自動トンネルで送る（SIA）

- 時間: 15 分 / 前提: なし / 使う画面: SD-WAN Manager、ポータルの説明（CSA の画面のサンプル）

## 目的

SIA（Secure Internet Access）は、拠点のインターネット向けの通信を CSA を通して出す形です。
SD-WAN Manager の Policy Group だけで、site-172 のルータ（C8KV-172）から CSA に IPsec のトンネルが自動で張られる様子を見ます。

## 流れ

| 手順 | やること | 確認すること | 確認 |
|---|---|---|---|
| 1 Policy Group | **Configuration** > **Policy Groups** で `SHOW-AWS-SIA` を開く | Application priority と Secure Internet Access の 2 つの部品。付いている機器は C8KV-172 の 1 台 | 自己申告 |
| 2 CSA に向ける方針 | Application Priority の表を読む | — | クイズ（CSA のトンネルに向けているもの） |
| 3 トンネルとトラッカー | **Monitor** > **Devices** で C8KV-172 を開き、Tunnel16000001 と Tunnel16000002 を探す | 2 本とも up | クイズ（ふだん通信を運ぶトンネル） |
| 4 CSA のトンネルグループ | 説明を読む（CSA の画面のサンプル） | — | 自己申告 |
| 5 端末から見た出口 | 説明を読む（端末 VM の送信元の IP） | — | クイズ（トンネルが 2 本とも落ちたとき） |
| 6 CSA のアクティビティ | 説明を読む（CSA の Activity Search のサンプル） | — | 自己申告 |

## 補足

- BASE-04 の手順 5（インターネット向けの通信が data policy で SSE TUNNEL に向く）と同じ仕組みです
