## git-tips
>   [git-tips](http://git.io/git-tips)が本家です。

[English](http://git.io/git-tips) | [中文](https://github.com/521xueweihan/git-tips) | [Русский](https://github.com/Imangazaliev/git-tips) | [한국어](https://github.com/mingrammer/git-tips) | [Tiếng Việt](https://github.com/hprobotic/git-tips)

### __ツール:__

[git-tip](https://www.npmjs.com/package/git-tip) -以下に紹介するtipsを実際に試すことができるCLIツールです。 ([Here in Docker container](https://github.com/djoudi5/docker-git-tip))
>  tipsを追加したい場合は[contributing.md](./contributing.md)を確認してください。

P.S:  `git version 2.7.4 (Apple Git-66)`で動作検証をしています。

<!-- @doxie.inject start toc -->
<!-- Don’t remove or change the comment above – that can break automatic updates. -->
* [Git公式の基本的なコマンドのサンプルを表示する](#Git公式の基本的なコマンドのサンプルを表示する)
* [Git公式のヘルプを表示する](#Git公式のヘルプを表示する)
* [コミットメッセージからコミットを検索する](#コミットメッセージからコミットを検索する)
* [リモートブランチと同期してローカルの変更を上書きする](#リモートブランチと同期してローカルの変更を上書きする)
* [特定のコミット時点で管理されている全ファイルを表示する](#特定のコミット時点で管理されている全ファイルを表示する)
* [ファーストコミットを取り消す](#ファーストコミットを取り消す)
* [全てのコンフリクトしているファイルを表示する](#全てのコンフリクトしているファイルを表示する)
* [特定のコミットで変更されたファイルを表示する](#特定のコミットで変更されたファイルを表示する)
* [最終コミットからステージングされていない変更を表示する](#最終コミットからステージングされていない変更を表示する)
* [コミット対象のステージングされている変更を表示する](#コミット対象のステージングされている変更を表示する)
* [ステージングされている変更とされていない変更の両方を表示する](#ステージングされている変更とされていない変更の両方を表示する)
* [masterにマージ済みのブランチを表示する](#masterにマージ済みのブランチを表示する)
* [前にいたブランチに素早く移動する](#前にいたブランチに素早く移動する)
* [masterにマージ済みのブランチを削除する](#masterにマージ済みのブランチを削除する)
* [全てのブランチとその親ブランチを、最新のコミットと共に表示する](#全てのブランチとその親ブランチを、最新のコミットと共に表示する)
* [どのリモートブランチを追跡するか選択する](#どのリモートブランチを追跡するか選択する)
* [ローカルブランチを削除する](#ローカルブランチを削除する)
* [リモートブランチを削除する](#リモートブランチを削除する)
* [ローカルタグを削除する](#ローカルタグを削除する)
* [リモートタグを削除する](#リモートタグを削除する)
* [ローカルで変更したファイルをHEADまで戻す](#ローカルで変更したファイルをHEADまで戻す)
* [正反対のコミットを作ることで、元のコミットを取り消す](#正反対のコミットを作ることで、元のコミットを取り消す)
* [コミットを破棄する。ローカルブランチのみで行うことを推奨](#コミットを破棄する。ローカルブランチのみで行うことを推奨)
* [直前のコミットのコメントを変更する](#直前のコミットのコメントを変更する)
* [現在のブランチのコミット履歴を表示する](#現在のブランチのコミット履歴を表示する)
* [直前のコミットの実行者を変更する](#直前のコミットの実行者を変更する)
* [直前のコミットの実行者をデフォルト値にリセットする](#直前のコミットの実行者をデフォルト値にリセットする)
* [リモートブランチのURLを変更する](#リモートブランチのURLを変更する)
* [現在設定されている全てのリモートブランチを表示する](#現在設定されている全てのリモートブランチを表示する)
* [ローカルとリモートの全部ランチを表示する](#ローカルとリモートの全部ランチを表示する)
* [リモートのブランチを表示する](#リモートのブランチを表示する)
* [ファイル全体ではなく、ファイル中の一部変更点だけをステージングする](#ファイル全体ではなく、ファイル中の一部変更点だけをステージングする)
* [gitの補完機能をインストールする](#gitの補完機能をインストールする)
* [直近２週間の変更点を表示する](#直近２週間の変更点を表示する)
* [masterからforkした時点よりあとのコミット履歴を表示](#masterからforkした時点よりあとのコミット履歴を表示)
* [コミットを別のブランチにcherry-pickする](#コミットを別のブランチにcherry-pickする)
* [特定のコミットが含まれているブランチを表示する](#特定のコミットが含まれているブランチを表示する)
* [エイリアスを作成する](#エイリアスを作成する)
* [前回コミットからの変更を一時保存する](#前回コミットからの変更を一時保存する)
* [前回コミットからの変更のうち、ステージングされていない変更を一時保存する](#前回コミットからの変更のうち、ステージングされていない変更を一時保存する)
* [前回コミットからの変更をgit管理されていないファイルの変更も含めて一時保管する](#前回コミットからの変更をgit管理されていないファイルの変更も含めて一時保管する)
* [前回コミットからの変更を名前をつけて一時保管する](#前回コミットからの変更を名前をつけて一時保管する)
* [前回コミットからの変更を全て一時保存する(ignoredしている、git管理されていない、git管理されている)](#前回コミットからの変更を全て一時保存する(ignoredしている、git管理されていない、git管理されている))
* [現在保存されているstashを表示する](#現在保存されているstashを表示する)
* [stashリストから削除せずに変更を適用する](#stashリストから削除せずに変更を適用する)
* [最後のstashを適用し、適用したstashは削除する](#適用したstashは削除する)
* [stashを全て削除する](#stashを全て削除する)
* [stashから1ファイルだけ取り出す](#stashから1ファイルだけ取り出す)
* [git管理しているファイルを全て表示する](#git管理しているファイルを全て表示する)
* [git管理していないファイルを全て表示する](#show-all-untracked-files)
* [gitignoreで無視しているファイルを全て表示する](#gitignoreで無視しているファイルを全て表示する)
* [リポジトリーからワーキングツリーを作成する (git 2.5)](#リポジトリーからワーキングツリーを作成する-(git 2.5))
* [HEADからワーキングツリーを作成する](#HEADからワーキングツリーを作成する)
* [ファイルをGit管理下から外す。ファイルは削除しない](#ファイルをGit管理下から外す。ファイルは削除しない)
* [git管理していないファイル/ディレクトリを削除する前に、ドライランで削除される対象を表示する](#git管理していないファイル/ディレクトリを削除する前に、ドライランで削除される対象を表示する)
* [git管理していないファイルを強制削除する](#git管理していないファイルを強制削除する)
* [git管理していないディレクトリーを強制削除する](#git管理していないディレクトリーを強制削除する)
* [全てのサブモジュールをアップデートする](#全てのサブモジュールをアップデートする)
* [現在のブランチでmasterにマージされていないコミットを表示する](#現在のブランチでmasterにマージされていないコミットを表示する)
* [ブランチ名を変更する](#ブランチ名を変更する)
* [featureブランチをmasterにrebaseして、その後masterにマージする](#featureブランチをmasterにrebaseして、その後masterにマージする)
* [masterブランチをアーカイブする](#masterブランチをアーカイブする)
* [前回のコミットをメッセージを除いて変更する](#前回のコミットをメッセージを除いて変更する)
* [リモートブランチで削除されているブランチへの参照を取り除く](#リモートブランチで削除されているブランチへの参照を取り除く)
* [一番最初のコミットのハッシュを取得する](#一番最初のコミットのハッシュを取得する)
* [バージョンツリーを描画する](#バージョンツリーを描画する)
* [reflogsから参照されているコミットを含めてバージョンツリーを描画する](#reflogsから参照されているコミットを含めてバージョンツリーを描画する)
* [指定したサブツリーだけをoriginにpushする](#指定したサブツリーだけをoriginにpushする)
* [サブツリーを現在のリポジトリに追加する](#サブツリーを現在のリポジトリに追加する)
* [指定したサブツリーだけをpullする](#指定したサブツリーだけをpullする)
* [指定したブランチをファイルに出力する](#指定したブランチをファイルに出力する)
* [バンドルからインポートする](#バンドルからインポートする)
* [現在のブランチ名を表示する](#現在のブランチ名を表示する)
* [コミット時に特定の1ファイルだけ無視する (e.g. Changelog)](#コミット時に特定の1ファイルだけ無視する-(e.g.-Changelog))
* [rebaseする前にstashする](#rebaseする前にstashする)
* [プルリクエストをID指定でローカルブランチにfetchする](#プルリクエストをID指定でローカルブランチにfetchする)
* [現在のブランチの一番直近のタグを表示する](#現在のブランチの一番直近のタグを表示する)
* [単語単位のdiffを表示する](#単語単位のdiffを表示する)
* [一般的なdiffツールで変更を表示する](#一般的なdiffツールで変更を表示する)
* [git管理しているファイルの変更を無視する](#git管理しているファイルの変更を無視する)
* [assume-unchangedを無効にする](#unchangedを無効にする)
* [.gitignoreに記載があるファイルを削除する](#.gitignoreに記載があるファイルを削除する)
* [削除したファイルを元に戻す](#削除したファイルを元に戻す)
* [特定のコミットハッシュまでファイルを戻す](#特定のコミットハッシュまでファイルを戻す)
* [pullしたときにmergeではなくrebaseするよう変更する](#pullしたときにmergeではなくrebaseするよう変更する)
* [全てのコンフィグとエイリアスの一覧を表示する](#全てのコンフィグとエイリアスの一覧を表示する)
* [ファイル名の大文字小文字変更を検知するように変更する](#make-git-case-sensitive)
* [カスタムエディターを追加する](#add-custom-editors)
* [誤字を自動修正する](#auto-correct-typos)
* [指定のハッシュが、どのブランチにいるかを表示する](#check-if-the-change-was-a-part-of-a-release)
* [ドライラン(ドライランをサポートしているコマンドに対して実行できる)](#dry-run-any-command-that-supports-dry-run-flag-should-do)
* [コミットを前回のコミットの修正としてマークする](#marks-your-commit-as-a-fix-of-a-previous-commit)
* [rebase時に上記のコミット順を隣に並べ替えてわかりやすくする](#rebase時に上記のコミット順を隣に並べ替えてわかりやすくする)
* [指定したファイルだけコミットする](#指定したファイルだけコミットする)
* [インタラクティブにステージングする](#インタラクティブにステージングする)
* [gitが無視しているファイルを表示する](#gitが無視しているファイルを表示する)
* [gitが無視しているファイルのステータスを表示する](#gitが無視しているファイルのステータスを表示する)
* [Branch1には入っていて、Branch2に入っていないコミットを表示する](#Branch1には入っていて、Branch2に入っていないコミットを表示する)
* [直近n個のコミットログを表示する](#直近n個のコミットログを表示する)
* [コンフリクトの解決法を記録してお、今後同じ理由でのコンフリクトが見つかったら同じ方法で自動的に解決する](#コンフリクトの解決法を記録してお、今後同じ理由でのコンフリクトが見つかったら同じ方法で自動的に解決する)
* [コンフリクトしたファイルをエディタで開く](#コンフリクトしたファイルをエディタで開く)
* [現在のプロジェクトが使用しているオブジェクト数とディスク使用量を表示する](#現在のプロジェクトが使用しているオブジェクト数とディスク使用量を表示する)
* [到達不能オブジェクトを削除する](#到達不能オブジェクトを削除する)
* [作業リポジトリを gitwebで一時的にブラウジングする](#作業リポジトリを-gitwebで一時的にブラウジングする)
* [コミットログで署名も表示する](#コミットログで署名も表示する)
* [グローバル設定を削除する](#グローバル設定を削除する)
* [履歴を持たない新しい空ブランチを作成する](#履歴を持たない新しい空ブランチを作成する)
* [別ブランチのファイルを表示する](#別ブランチのファイルを表示する)
* [ルートとマージコミットのみ表示する](#ルートとマージコミットのみ表示する)
* [直前の2コミットをインタラクティブにrebaseする](#直前の2コミットをインタラクティブにrebaseする)
* [作業中のブランチを表示する](#作業中のブランチを表示する)
* [二分探索でバグの発生元を発見する](#二分探索でバグの発生元を発見する)
* [pre-commitフックが仕掛けられているときに、チェックをスルーしてコミットする](#pre-commitフックが仕掛けられているときに、チェックをスルーしてコミットする)
* [特定のファイルの変更履歴を表示する (リネームされていても)](#特定のファイルの変更履歴を表示する-(リネームされていても))
* [特定のブランチをクローンする](#特定のブランチをクローンする)
* [新しいブランチを作って移動する](#新しいブランチを作って移動する)
* [コミット時にファイルモードの変更を無視する](#コミット時にファイルモードの変更を無視する)
* [ターミナルの出力に色を付けない](#ターミナルの出力に色を付けない)
* [ターミナルの出力の色設定を個別に変更する](#ターミナルの出力の色設定を個別に変更する)
* [ローカルブランチを新しい順に表示する](#ローカルブランチを新しい順に表示する)
* [文字列か正規表現でgit管理下のファイルの行を検索する](#文字列か正規表現でgit管理下のファイルの行を検索する)
* [最新のリポジトリだけcloneする](#最新のリポジトリだけcloneする)
* [指定の文字で全てのブランチのコミットログを検索する](#指定の文字で全てのブランチのコミットログを検索する)
* [masterから指定のブランチに向けての最初のコミットを表示する](#masterから指定のブランチに向けての最初のコミットを表示する)
* [ステージングしたファイルをステージングする前に戻す](#ステージングしたファイルをステージングする前に戻す)
* [リモートリポジトリに強制的にpushする](#リモートリポジトリに強制的にpushする)
* [リモートリポジトリを追加する](#リモートリポジトリを追加する)
* [ファイルの全行に対して、最終更新日と更新者を表示する](#ファイルの全行に対して、最終更新日と更新者を表示する)
* [ユーザ毎のコミット回数とメッセージを一覧表示する](#ユーザ毎のコミット回数とメッセージを一覧表示する)
* [誰かの作業を上書きしない場合、リモートに強制的にpushする](#誰かの作業を上書きしない場合、リモートに強制的にpushする)
* [ユーザが貢献した行数を表示する](#ユーザが貢献した行数を表示する)
* [リバート:全てのマージをリバートする](#リバート:全てのマージをリバートする)
* [ブランチのコミット回数を表示する](#ブランチのコミット回数を表示する)
* [エイリアス: git undo](#エイリアス:-git-undo)
* [オブジェクトノートを追加する](#オブジェクトノートを追加する)
* [全てのオブジェクトノートを表示する](#全てのオブジェクトノートを表示する)
* [別のリポジトリからコミットを適用する](#別のリポジトリからコミットを適用する)
* [特定のリモートブランチからfetchする](#特定のリモートブランチからfetchする)
* [2ブランチから共通の祖先を見付ける](#2ブランチから共通の祖先を見付ける)
* [pushしてないコミットを表示する](#pushしてないコミットを表示する)
* [空白以外の変更をapplyする](#空白以外の変更をapplyする)
* [ローカル/グローバルのgitコンフィグを編集する](#ローカル/グローバルのgitコンフィグを編集する)
* [指定範囲内をblameする](#指定範囲内をblameする)
* [git変数を表示する](#git変数を表示する)
* [整形済みのパッチを作成する](#整形済みのパッチを作成する)
* [リポジトリのルート絶対パスを取得する](#リポジトリのルート絶対パスを取得する)
* [特定期間のログを表示する](#特定期間のログを表示する)
* [指定者以外のログを表示する](#指定者以外のログを表示する)
* [ペンディング中の変更のまとめを作成](#ペンディング中の変更のまとめを作成)
* [リモートリポジトリのブランチを表示する](#リモートリポジトリのブランチを表示する)
* [git管理していないファイルをバックアップする](#git管理していないファイルをバックアップする)
* [エイリアスを一覧表示する](#エイリアスを一覧表示する)
* [git statusを簡潔に表示する](#statusを簡潔に表示する)
* [昨日のコミットをチェックアウトする](#昨日のコミットをチェックアウトする)
* [ローカルブランチをリモートリポジトリにpushして追跡する](#ローカルブランチをリモートリポジトリにpushして追跡する)
* [ブランチのベースを変更する](#ブランチのベースを変更する)
* [HTTPsではなくSSHをリモートへの接続に使用する](#HTTPsではなくSSHをリモートへの接続に使用する)

<!-- Don’t remove or change the comment below – that can break automatic updates. More info at <http://npm.im/doxie.inject>. -->
<!-- @doxie.inject end toc -->


<!-- @doxie.inject start -->
<!-- Don’t remove or change the comment above – that can break automatic updates. -->
## Git公式の基本的なコマンドのサンプルを表示する
```sh
git help everyday
```

## Git公式のヘルプを表示する
```sh
git help -g
```

## コミットメッセージからコミットを検索する
```sh
git log -S'<a term in the source>'
```

## リモートブランチと同期してローカルの変更を上書きする
```sh
git fetch origin && git reset --hard origin/master && git clean -f -d
```

## 特定のコミット時点で管理されている全ファイルを表示する
```sh
git ls-tree --name-only -r <commit-ish>
```

## ファーストコミットを取り消す
```sh
git update-ref -d HEAD
```

## 全てのコンフリクトしているファイルを表示する
```sh
git diff --name-only --diff-filter=U
```

## 特定のコミットで変更されたファイルを表示する
```sh
git diff-tree --no-commit-id --name-only -r <commit-ish>
```

## 最終コミットからステージングされていない変更を表示する
```sh
git diff
```

## コミット対象のステージングされている変更を表示する
```sh
git diff --cached
```


__Alternatives:__
```sh
git diff --staged
```

## ステージングされている変更とされていない変更の両方を表示する
```sh
git diff HEAD
```

## masterにマージ済みのブランチを表示する
```sh
git branch --merged master
```

## 前にいたブランチに素早く移動する
```sh
git checkout -
```


__Alternatives:__
```sh
git checkout @{-1}
```

## masterにマージ済みのブランチを削除する
```sh
git branch --merged master | grep -v '^\*' | xargs -n 1 git branch -d
```


__Alternatives:__
```sh
git branch --merged master | grep -v '^\*\|  master' | xargs -n 1 git branch -d # will not delete master if master is not checked out
```

## 全てのブランチとその親ブランチを、最新のコミットと共に表示する
```sh
git branch -vv
```

## どのリモートブランチを追跡するか選択する
```sh
git branch -u origin/mybranch
```

## ローカルブランチを削除する
```sh
git branch -d <local_branchname>
```

## リモートブランチを削除する
```sh
git push origin --delete <remote_branchname>
```


__Alternatives:__
```sh
git push origin :<remote_branchname>
```

## ローカルタグを削除する
```sh
git tag -d <tag-name>
```

## リモートタグを削除する
```sh
git push origin :refs/tags/<tag-name>
```

## ローカルで変更したファイルをHEADまで戻す
```sh
git checkout -- <file_name>
```

## 正反対のコミットを作ることで、元のコミットを取り消す
```sh
git revert <commit-ish>
```

## コミットを破棄する。ローカルブランチのみで行うことを推奨
```sh
git reset <commit-ish>
```

## 直前のコミットのコメントを変更する
```sh
git commit -v --amend
```

## 現在のブランチのコミット履歴を表示する
```sh
git cherry -v master
```

## 直前のコミットの実行者を変更する
```sh
git commit --amend --author='Author Name <email@address.com>'
```

## R直前のコミットの実行者をデフォルト値にリセットする
```sh
git commit --amend --reset-author --no-edit
```

## リモートブランチのURLを変更する
```sh
git remote set-url origin <URL>
```

## 現在設定されている全てのリモートブランチを表示する
```sh
git remote
```


__Alternatives:__
```sh
git remote show
```

## ローカルとリモートの全部ランチを表示する
```sh
git branch -a
```

## リモートのブランチを表示する
```sh
git branch -r
```

## ファイル全体ではなく、ファイル中の一部変更点だけをステージングする
```sh
git add -p
```

## gitの補完機能をインストールする
```sh
curl -L http://git.io/vfhol > ~/.git-completion.bash && echo '[ -f ~/.git-completion.bash ] && . ~/.git-completion.bash' >> ~/.bashrc
```

## 直近２週間の変更点を表示する
```sh
git log --no-merges --raw --since='2 weeks ago'
```


__Alternatives:__
```sh
git whatchanged --since='2 weeks ago'
```

## masterからforkした時点よりあとのコミット履歴を表示
```sh
git log --no-merges --stat --reverse master..
```

## コミットを別のブランチにcherry-pickする
```sh
git checkout <branch-name> && git cherry-pick <commit-ish>
```

## 特定のコミットが含まれているブランチを表示する
```sh
git branch -a --contains <commit-ish>
```


__Alternatives:__
```sh
git branch --contains <commit-ish>
```

## エイリアスを作成する
```sh
git config --global alias.<handle> <command> 
git config --global alias.st status
```

## 前回コミットからの変更を一時保存する
```sh
git stash
```


__Alternatives:__
```sh
git stash save
```

## 前回コミットからの変更のうち、ステージングされていない変更を一時保存する
```sh
git stash -k
```


__Alternatives:__
```sh
git stash --keep-index
```


```sh
git stash save --keep-index
```

## 前回コミットからの変更をgit管理されていないファイルの変更も含めて一時保管する
```sh
git stash -u
```


__Alternatives:__
```sh
git stash save -u
```


```sh
git stash save --include-untracked
```

## 前回コミットからの変更を名前をつけて一時保管する
```sh
git stash save <message>
```

## 前回コミットからの変更を全て一時保存する(ignoredしている、git管理されていない、git管理されている)
```sh
git stash -a
```


__Alternatives:__
```sh
git stash --all
```


```sh
git stash save --all
```

## 現在保存されているstashを表示する
```sh
git stash list
```

## stashリストから削除せずに変更を適用する
```sh
git stash apply <stash@{n}>
```

## 最後のstashを適用し、適用したstashは削除する
```sh
git stash pop
```


__Alternatives:__
```sh
git stash apply stash@{0} && git stash drop stash@{0}
```

## stashを全て削除する
```sh
git stash clear
```


__Alternatives:__
```sh
git stash drop <stash@{n}>
```

## stashから1ファイルだけ取り出す
```sh
git checkout <stash@{n}> -- <file_path>
```


__Alternatives:__
```sh
git checkout stash@{0} -- <file_path>
```

## git管理しているファイルを全て表示する
```sh
git ls-files -t
```

## git管理していないファイルを全て表示する
```sh
git ls-files --others
```

## gitignoreで無視しているファイルを全て表示する
```sh
git ls-files --others -i --exclude-standard
```

## リポジトリーからワーキングツリーを作成する (git 2.5)
```sh
git worktree add -b <branch-name> <path> <start-point>
```

## HEADからワーキングツリーを作成する
```sh
git worktree add --detach <path> HEAD
```

## ファイルをGit管理下から外す。ファイルは削除しない
```sh
git rm --cached <file_path>
```


__Alternatives:__
```sh
git rm --cached -r <directory_path>
```

## git管理していないファイル/ディレクトリを削除する前に、ドライランで削除される対象を表示する
```sh
git clean -n
```

## git管理していないファイルを強制削除する
```sh
git clean -f
```

## forcefully-remove-untracked-directory
```sh
git clean -f -d
```

## 全てのサブモジュールをアップデートする
```sh
git submodule foreach git pull
```


__Alternatives:__
```sh
git submodule update --init --recursive
```


```sh
git submodule update --remote
```

## 現在のブランチでmasterにマージされていないコミットを表示する
```sh
git cherry -v master
```


__Alternatives:__
```sh
git cherry -v master <branch-to-be-merged>
```

## ブランチ名を変更する
```sh
git branch -m <new-branch-name>
```


__Alternatives:__
```sh
git branch -m [<old-branch-name>] <new-branch-name>
```

## featureブランチをmasterにrebaseして、その後masterにマージする
```sh
git rebase master feature && git checkout master && git merge -
```

## masterブランチをアーカイブする
```sh
git archive master --format=zip --output=master.zip
```

## 前回のコミットをメッセージを除いて変更する
```sh
git add --all && git commit --amend --no-edit
```

## リモートブランチで削除されているブランチへの参照を取り除く
```sh
git fetch -p
```


__Alternatives:__
```sh
git remote prune origin
```

## 一番最初のコミットのハッシュを取得する
```sh
 git rev-list --reverse HEAD | head -1
```


__Alternatives:__
```sh
git rev-list --max-parents=0 HEAD
```


```sh
git log --pretty=oneline | tail -1 | cut -c 1-40
```


```sh
git log --pretty=oneline --reverse | head -1 | cut -c 1-40
```

## バージョンツリーを描画する
```sh
git log --pretty=oneline --graph --decorate --all
```


__Alternatives:__
```sh
gitk --all
```


```sh
git log --graph --pretty=format:'%C(auto) %h | %s | %an | %ar%d'
```

## reflogsから参照されているコミットを含めてバージョンツリーを描画する
```sh
git log --graph --decorate --oneline $(git rev-list --walk-reflogs --all)
```

## 指定したサブツリーだけをoriginにpushする
```sh
git subtree push --prefix subfolder_name origin gh-pages
```

## サブツリーを現在のリポジトリに追加する
```sh
git subtree add --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## 指定したサブツリーだけをpullする
```sh
git subtree pull --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## 指定したブランチをファイルに出力する
```sh
git bundle create <file> <branch-name>
```

## バンドルからインポートする
```sh
git clone repo.bundle <repo-dir> -b <branch-name>
```

## 現在のブランチ名を表示する
```sh
git rev-parse --abbrev-ref HEAD
```

## コミット時に特定の1ファイルだけ無視する (e.g. Changelog)
```sh
git update-index --assume-unchanged Changelog; git commit -a; git update-index --no-assume-unchanged Changelog
```

## rebaseする前にstashする
```sh
git rebase --autostash
```

## rebaseする前にstashする
```sh
git fetch origin pull/<id>/head:<branch-name>
```


__Alternatives:__
```sh
git pull origin pull/<id>/head:<branch-name>
```

## 現在のブランチの一番直近のタグを表示する
```sh
git describe --tags --abbrev=0
```

## 単語単位のdiffを表示する
```sh
git diff --word-diff
```

## 一般的なdiffツールで変更を表示する
```sh
git difftool [-t <tool>] <commit1> <commit2> <path>
```

## git管理しているファイルの変更を無視する
```sh
git update-index --assume-unchanged <file_name>
```

## unchangedを無効にする
```sh
git update-index --no-assume-unchanged <file_name>
```

## .gitignoreに記載があるファイルを削除する
```sh
git clean -X -f
```

## 削除したファイルを元に戻す
```sh
git checkout <deleting_commit>^ -- <file_path>
```

## 特定のコミットハッシュまでファイルを戻す
```sh
git checkout <commit-ish> -- <file_path>
```

## pullしたときにmergeではなくrebaseするよう変更する
```sh
git config --global pull.rebase true
```


__Alternatives:__
```sh
#git < 1.7.9
git config --global branch.autosetuprebase always
```

## 全てのコンフィグとエイリアスの一覧を表示する
```sh
git config --list
```

## ファイル名の大文字小文字変更を検知するように変更する
```sh
git config --global core.ignorecase false
```

## カスタムエディターを追加する
```sh
git config --global core.editor '$EDITOR'
```

## 誤字を自動修正する
```sh
git config --global help.autocorrect 1
```

## どのブランチにいるかを表示する
```sh
git name-rev --name-only <SHA-1>
```

## ドライラン(ドライランをサポートしているコマンドに対して実行できる)
```sh
git clean -fd --dry-run
```

## コミットを前回のコミットの修正としてマークする
```sh
git commit --fixup <SHA-1>
```

## rebase時に上記のコミット順を隣に並べ替えてわかりやすくする
```sh
git rebase -i --autosquash
```

## 指定したファイルだけコミットする
```sh
git commit --only <file_path>
```

## インタラクティブにステージングする
```sh
git add -i
```

## gitが無視しているファイルを表示する
```sh
git check-ignore *
```

## gitが無視しているファイルのステータスを表示する
```sh
git status --ignored
```

## Branch1には入っていて、Branch2に入っていないコミットを表示する
```sh
git log Branch1 ^Branch2
```

## 直近n個のコミットログを表示する
```sh
git log -<n>
```


__Alternatives:__
```sh
git log -n <n>
```

## コンフリクトの解決法を記録してお、今後同じ理由でのコンフリクトが見つかったら同じ方法で自動的に解決する
```sh
git config --global rerere.enabled 1
```

## コンフリクトしたファイルをエディタで開く
```sh
git diff --name-only | uniq | xargs $EDITOR
```

## 現在のプロジェクトが使用しているオブジェクト数とディスク使用量を表示する
```sh
git count-objects --human-readable
```

## 到達不能オブジェクトを削除する
```sh
git gc --prune=now --aggressive
```

## 作業リポジトリを gitwebで一時的にブラウジングする
```sh
git instaweb [--local] [--httpd=<httpd>] [--port=<port>] [--browser=<browser>]
```

## コミットログで署名も表示する
```sh
git log --show-signature
```

## グローバル設定を削除する
```sh
git config --global --unset <entry-name>
```

## 履歴を持たない新しい空ブランチを作成する
```sh
git checkout --orphan <branch_name>
```

## 別ブランチのファイルを表示する
```sh
git show <branch_name>:<file_name>
```

## ルートとマージコミットのみ表示する
```sh
git log --first-parent
```

## 直前の2コミットをインタラクティブにrebaseする
```sh
git rebase --interactive HEAD~2
```

## 作業中のブランチを表示する
```sh
git checkout master && git branch --no-merged
```

## 二分探索でバグの発生元を発見する
```sh
git bisect start                    # Search start 
git bisect bad                      # Set point to bad commit 
git bisect good v2.6.13-rc2         # Set point to good commit|tag 
git bisect bad                      # Say current state is bad 
git bisect good                     # Say current state is good 
git bisect reset                    # Finish search 

```

## pre-commitフックが仕掛けられているときに、チェックをスルーしてコミットする
```sh
git commit --no-verify
```

## 特定のファイルの変更履歴を表示する (リネームされていても)
```sh
git log --follow -p -- <file_path>
```

## 特定のブランチをクローンする
```sh
git clone -b <branch-name> --single-branch https://github.com/user/repo.git
```

## 新しいブランチを作って移動する
```sh
git checkout -b <branch-name>
```


__Alternatives:__
```sh
git branch <branch-name> && git checkout <branch-name>
```

## コミット時にファイルモードの変更を無視する
```sh
git config core.fileMode false
```

## ターミナルの出力に色を付けない
```sh
git config --global color.ui false
```

## ターミナルの出力の色設定を個別に変更する
```sh
git config --global <specific command e.g branch, diff> <true, false or always>
```

## ローカルブランチを新しい順に表示する
```sh
git for-each-ref --sort=-committerdate --format='%(refname:short)' refs/heads/
```

## 文字列か正規表現でgit管理下のファイルの行を検索する
```sh
git grep --heading --line-number 'foo bar'
```

## 最新のリポジトリだけcloneする
```sh
git clone https://github.com/user/repo.git --depth 1
```

## 指定の文字で全てのブランチのコミットログを検索する
```sh
git log --all --grep='<given-text>'
```

## masterから指定のブランチに向けての最初のコミットを表示する
```sh
git log --oneline master..<branch-name> | tail -1
```


__Alternatives:__
```sh
git log --reverse master..<branch-name> | head -6
```

## ステージングしたファイルをステージングする前に戻す
```sh
git reset HEAD <file-name>
```

## リモートリポジトリに強制的にpushする
```sh
git push -f <remote-name> <branch-name>
```

## リモートリポジトリを追加する
```sh
git remote add <remote-nickname> <remote-url>
```

## ファイルの全行に対して、最終更新日と更新者を表示する
```sh
git blame <file-name>
```

## ユーザ毎のコミット回数とメッセージを一覧表示する
```sh
git shortlog
```

## 誰かの作業を上書きしない場合、リモートに強制的にpushする
```sh
git push --force-with-lease <remote-name> <branch-name>
```

## ユーザが貢献した行数を表示する
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | gawk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s removed lines: %s total lines: %s
", add, subs, loc }' -
```


__Alternatives:__
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | awk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s, removed lines: %s, total lines: %s
", add, subs, loc }' - # on Mac OSX
```

## リバート:全てのマージをリバートする
```sh
git revert -m 1 <commit-ish>
```

## ブランチのコミット回数を表示する
```sh
git rev-list --count <branch-name>
```

## エイリアス: git undo
```sh
git config --global alias.undo '!f() { git reset --hard $(git rev-parse --abbrev-ref HEAD)@{${1-1}}; }; f'
```

## オブジェクトノートを追加する
```sh
git notes add -m 'Note on the previous commit....'
```

## 全てのオブジェクトノートを表示する
```sh
git log --show-notes='*'
```

## 別のリポジトリからコミットを適用する
```sh
git --git-dir=<source-dir>/.git format-patch -k -1 --stdout <SHA1> | git am -3 -k
```

## 特定のリモートブランチからfetchする
```sh
git fetch origin master:refs/remotes/origin/mymaster
```

## 2ブランチから共通の祖先を見付ける
```sh
diff -u <(git rev-list --first-parent BranchA) <(git rev-list --first-parent BranchB) | sed -ne 's/^ //p' | head -1
```

## pushしてないコミットを表示する
```sh
git log --branches --not --remotes
```


__Alternatives:__
```sh
git log @{u}..
```


```sh
git cherry -v
```

## 空白以外の変更をapplyする
```sh
git diff --ignore-all-space | git apply --cached
```

## ローカル/グローバルのgitコンフィグを編集する
```sh
git config [--global] --edit
```

## 指定範囲内をblameする
```sh
git blame -L <start>,<end>
```

## git変数を表示する
```sh
git var -l | <variable>
```

## 整形済みのパッチを作成する
```sh
git format-patch -M upstream..topic
```

## リポジトリのルート絶対パスを取得する
```sh
git rev-parse --show-toplevel
```

## 特定期間のログを表示する
```sh
git log --since='FEB 1 2017' --until='FEB 14 2017'
```

## 指定者以外のログを表示する
```sh
git log --perl-regexp --author='^((?!excluded-author-regex).*)

```

## ペンディング中の変更のまとめを作成
```sh
git request-pull v1.0 https://git.ko.xz/project master:for-linus
```

## リモートリポジトリのブランチを表示する
```sh
git ls-remote git://git.kernel.org/pub/scm/git/git.git
```

## git管理していないファイルをバックアップする
```sh
git ls-files --others -i --exclude-standard | xargs zip untracked.zip
```

## エイリアスを一覧表示する
```sh
git config -l | grep alias | sed 's/^alias\.//g'
```


__Alternatives:__
```sh
git config -l | grep alias | cut -d '.' -f 2
```

## git statusを簡潔に表示する
```sh
git status --short --branch
```

## 昨日のコミットをチェックアウトする
```sh
git checkout master@{yesterday}
```

## ローカルブランチをリモートリポジトリにpushして追跡する
```sh
git push -u origin <branch_name>
```

## ブランチのベースを変更する
```sh
git rebase --onto <new_base> <old_base>
```

## HTTPsではなくSSHをリモートへの接続に使用する
```sh
git config --global url.'git@github.com:'.insteadOf 'https://github.com/'
```

<!-- Don’t remove or change the comment below – that can break automatic updates. More info at <http://npm.im/doxie.inject>. -->
<!-- @doxie.inject end -->
