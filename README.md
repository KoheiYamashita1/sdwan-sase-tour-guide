# SD-WAN / SASE 体験ツアー ガイド（体験者向け）

Cisco Catalyst SD-WAN、Cisco Secure Access（CSA）、Security Cloud Control（SCC）、Cisco Cloud Control（CCC）を実機で連携させたショーケースを、
体験者として一通り回るためのガイドです。全体像、アジェンダ、構成、ツアーごとの流れをまとめています。

このリポジトリは体験者が読むものです。設定を変える手順や、管理者の作業は入っていません。
体験者のアカウントは読み取り専用で、ツアーの中で設定を変えることはありません。

## AI エージェントと一緒に進める

このリポジトリを AI エージェントに読み込ませると、エージェントが案内役になって、ツアーを最後まで進められます。
エージェントへの指示は `AGENTS.md` にあります。エージェントには、たとえば次のように頼んでください。

```text
このリポジトリを読んで、SD-WAN / SASE 体験ツアーを最初から案内してください。
```

## 読む順番

| 順番 | 文書 | 中身 |
|---|---|---|
| 1 | [docs/01_overview.md](docs/01_overview.md) | 全体像。何を体験するか、体験者ができること・できないこと |
| 2 | [docs/02_agenda.md](docs/02_agenda.md) | アジェンダ。ツアーの順番と所要時間 |
| 3 | [docs/03_architecture.md](docs/03_architecture.md) | 構成。拠点、コントローラ、CSA、SCC、席のつながり |
| 4 | [docs/04_before-you-start.md](docs/04_before-you-start.md) | 始める前の準備。受け取るもの、ログインの流れ |
| 5 | [tours/](tours/) | ツアーごとの流れ（10 本） |
| 6 | [docs/05_troubleshooting.md](docs/05_troubleshooting.md) | うまくいかないとき |
| 7 | [docs/06_completion.md](docs/06_completion.md) | 完了の条件と、終わったあとにすること |

## 構成

```text
sdwan-sase-tour-guide/
├── README.md        この文書
├── AGENTS.md        案内役の AI エージェントへの指示
├── .github/         感想を送る Issue のフォーム
├── docs/            全体像、アジェンダ、構成、準備、困ったとき、完了の条件
├── tours/           ツアーごとの流れ（BASE-01〜05、SCC-01、SSE-01〜03、CCC-01）
└── images/          全体の構成図（tour-overview.svg）
```

## 感想を送る

体験の感想は、ツアーの改善に使います。送り方は 2 つです。

1. **体験ポータルのアンケート（おすすめ）**: 10 本をクリアすると出ます。5 問に答えると、修了の資料（PoC / PoV の計画書）をダウンロードできます。記述は、公開に同意したときだけ、匿名でこのリポジトリの Issue に載ります
2. **このリポジトリの Issue**: GitHub のアカウントがあれば、[Issue のフォーム](../../issues/new?template=feedback.yml)から送れます

このリポジトリは公開されています。Issue に、会社名、お名前、メールアドレス、パスワード、社内の URL を書かないでください。
いただいた感想は、運営者が採用（`feedback:accepted`）、見送り（`feedback:rejected`）、保留（`feedback:hold`）に分け、採用したものをツアーとガイドに反映します。

## 大事なこと

- 体験ポータルに出る手順の文が正本です。このガイドはその大まかな流れで、画面の名前や値が違うときはポータルに従ってください
- パスワードなどの資格情報は、このリポジトリにもエージェントとの会話にも書きません。ポータルや配られたものを見て、自分で入力します
- SD-WAN Manager は本物の環境です。保存やデプロイができそうに見えたら、そこで止めて会場の担当者に知らせてください
