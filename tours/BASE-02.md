# BASE-02 オーバーレイの状態（制御接続、TLOC、BFD）

- 時間: 10 分 / 前提: BASE-01 / 使う画面: SD-WAN Manager

## 目的

拠点のルータは、まずコントローラと制御接続を張り、WAN の回線ごとに TLOC を持ち、拠点どうしで BFD を使ってトンネルの品質を測ります。
AWS の 3 拠点（site-171〜173）のルータで、これを画面で確かめます。

## 流れ

| 手順 | やること | 確認すること | 確認 |
|---|---|---|---|
| 1 機器を探す | **Monitor** > **Devices** で C8KV-171、172、173 を探す | 3 台とも reachable | live（ポータルが site-171 の制御接続を確かめる） |
| 2 制御接続 | C8KV-171 を開き、**Control Connections** を見る | vSmart と vManage への接続が up | クイズ（経路を配るコントローラはどれか） |
| 3 TLOC | 同じ機器の **TLOC** を見る | WAN1（GigabitEthernet1）の color | クイズ（WAN1 の color） |
| 4 トンネルと BFD | **BFD Sessions**（または **Monitor** > **Tunnels**）を見る | 17.1.1.2 と 17.1.1.3 への 2 本が up（フルメッシュ） | 自己申告 |

## 補足

- 手順 1 の live の確認が「確認できませんでした」になったら、画面で 3 台が reachable なことを見てから自己申告に切り替えます（[困ったとき](../docs/05_troubleshooting.md)）
- BFD で測る遅延、ロス、ジッタは、経路の選択（Application Aware Routing）の材料になります
