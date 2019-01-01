## git-tips
>  `git-tips`の一覧です。tipsを追加したい場合は[contributing.md](./contributing.md)を確認してください。

[English](http://git.io/git-tips) | [中文](https://github.com/521xueweihan/git-tips) | [Русский](https://github.com/Imangazaliev/git-tips) | [한국어](https://github.com/mingrammer/git-tips) | [Tiếng Việt](https://github.com/hprobotic/git-tips)

### __Tools:__

* [git-tip](https://www.npmjs.com/package/git-tip) -以下に紹介するtipsを実際に試すことができるCLIツールです。 ([Here in Docker container](https://github.com/djoudi5/docker-git-tip))

P.S:  `git version 2.7.4 (Apple Git-66)`で動作検証をしています。

<!-- @doxie.inject start toc -->
<!-- Don’t remove or change the comment above – that can break automatic updates. -->
* [Git公式の基本的なコマンドのサンプルを表示する](#everyday-git-in-twenty-commands-or-so)
* [Git公式のヘルプを表示する](#show-helpful-guides-that-come-with-git)
* [コミットメッセージからコミットを検索する](#search-change-by-content)
* [リモートブランチと同期してローカルの変更を上書きする](#sync-with-remote-overwrite-local-changes)
* [特定のコミット時点で管理されている全ファイルを表示する](#list-of-all-files-till-a-commit)
* [ファーストコミットを取り消す](#git-reset-first-commit)
* [全てのコンフリクトしているファイルを表示する](#list-all-the-conflicted-files)
* [特定のコミットで変更されたファイルを表示する](#list-of-all-files-changed-in-a-commit)
* [最終コミットからステージングされていない変更を表示する](#unstaged-changes-since-last-commit)
* [コミット対象のステージングされている変更を表示する](#changes-staged-for-commit)
* [ステージングされている変更とされていない変更の両方を表示する](#show-both-staged-and-unstaged-changes)
* [masterにマージ済みのブランチを表示する](#list-all-branches-that-are-already-merged-into-master)
* [前にいたブランチに素早く移動する](#quickly-switch-to-the-previous-branch)
* [masterにマージ済みのブランチを削除する](#remove-branches-that-have-already-been-merged-with-master)
* [全てのブランチとその親ブランチを、最新のコミットと共に表示する](#list-all-branches-and-their-upstreams-as-well-as-last-commit-on-branch)
* [どのリモートブランチを追跡するか選択する](#track-upstream-branch)
* [ローカルブランチを削除する](#delete-local-branch)
* [リモートブランチを削除する](#delete-remote-branch)
* [ローカルタグを削除する](#delete-local-tag)
* [リモートタグを削除する](#delete-remote-tag)
* [ローカルで変更したファイルをHEADまで戻す](#undo-local-changes-with-the-last-content-in-head)
* [正反対のコミットを作ることで、元のコミットを取り消す](#revert-undo-a-commit-by-creating-a-new-commit)
* [コミットを破棄する。ローカルブランチのみで行うことを推奨](#reset-discard-commits-advised-for-private-branch)
* [直前のコミットのコメントを変更する](#reword-the-previous-commit-message)
* [現在のブランチのコミット履歴を表示する](#see-commit-history-for-just-the-current-branch)
* [直前のコミットの実行者を変更する](#amend-author)
* [直前のコミットの実行者をデフォルト値にリセットする](#reset-author-after-author-has-been-changed-in-the-global-config)
* [リモートブランチのURLを変更する](#changing-a-remotes-url)
* [現在設定されている全てのリモートブランチを表示する](#get-list-of-all-remote-references)
* [ローカルとリモートの全部ランチを表示する](#get-list-of-all-local-and-remote-branches)
* [リモートのブランチを表示する](#get-only-remote-branches)
* [ファイル全体ではなく、ファイル中の一部変更点だけをステージングする](#stage-parts-of-a-changed-file-instead-of-the-entire-file)
* [gitの補完機能をインストールする](#get-git-bash-completion)
* [直近２週間の変更点を表示する](#what-changed-since-two-weeks)
* [masterからforkした時点よりあとのコミット履歴を表示](#see-all-commits-made-since-forking-from-master)
* [コミットを別のブランチにcherry-pickする](#pick-commits-across-branches-using-cherry-pick)
* [特定のコミットが含まれているブランチを表示する](#find-out-branches-containing-commit-hash)
* [エイリアスを作成する](#git-aliases)
* [前回コミットからの変更を一時保存する](#saving-current-state-of-tracked-files-without-commiting)
* [前回コミットからの変更のうち、ステージングされていない変更を一時保存する](#saving-current-state-of-unstaged-changes-to-tracked-files)
* [前回コミットからの変更をgit管理されていないファイルの変更も含めて一時保管する](#saving-current-state-including-untracked-files)
* [前回コミットからの変更を名前をつけて一時保管する](#saving-current-state-with-message)
* [前回コミットからの変更を全て一時保存する (ignoredしている, git管理されていない git管理されている)](#saving-current-state-of-all-files-ignored-untracked-and-tracked)
* [現在保存されているstashを表示する](#show-list-of-all-saved-stashes)
* [stashリストから削除せずに変更を適用する](#apply-any-stash-without-deleting-from-the-stashed-list)
* [最後のstashを適用し、適用したstashは削除する](#apply-last-stashed-state-and-delete-it-from-stashed-list)
* [stashを全て削除する](#delete-all-stored-stashes)
* [stashから1ファイルだけ取り出す](#grab-a-single-file-from-a-stash)
* [git管理しているファイルを全て表示する](#show-all-tracked-files)
* [git管理していないファイルを全て表示する](#show-all-untracked-files)
* [gitignoreで無視しているファイルを全て表示する](#show-all-ignored-files)
* [リポジトリーからワーキングツリーを作成する (git 2.5)](#create-new-working-tree-from-a-repository-git-25)
* [HEADからワーキングツリーを作成する](#create-new-working-tree-from-head-state)
* [ファイルをGit管理下から外す。ファイルは削除しない](#untrack-files-without-deleting)
* [git管理していないファイル/ディレクトリを削除する前に、ドライランで削除される対象を表示する](#before-deleting-untracked-filesdirectory-do-a-dry-run-to-get-the-list-of-these-filesdirectories)
* [git管理していないファイルを強制削除する](#forcefully-remove-untracked-files)
* [git管理していないディレクトリーを強制削除する](#forcefully-remove-untracked-directory)
* [全てのサブモジュールをアップデートする](#update-all-the-submodules)
* [現在のブランチでmasterにマージされていないコミットを表示する](#show-all-commits-in-the-current-branch-yet-to-be-merged-to-master)
* [ブランチ名を変更する](#rename-a-branch)
* [featureブランチをmasterにrebaseして、その後masterにマージする](#rebases-feature-to-master-and-merges-it-in-to-master)
* [masterブランチをアーカイブする](#archive-the-master-branch)
* [前回のコミットをメッセージを除いて変更する](#modify-previous-commit-without-modifying-the-commit-message)
* [リモートブランチで削除されているブランチへの参照を取り除く](#prunes-references-to-remote-branches-that-have-been-deleted-in-the-remote)
* [一番最初のコミットのハッシュを取得する](#retrieve-the-commit-hash-of-the-initial-revision)
* [バージョンツリーを描画する](#visualize-the-version-tree)
* [reflogsから参照されているコミットを含めてバージョンツリーを描画する](#visualize-the-tree-including-commits-that-are-only-referenced-from-reflogs)
* [指定したサブツリーだけをoriginにpushする](#deploying-git-tracked-subfolder-to-gh-pages)
* [サブツリーを現在のリポジトリに追加する](#adding-a-project-to-repo-using-subtree)
* [指定したサブツリーだけをpullする](#get-latest-changes-in-your-repo-for-a-linked-project-using-subtree)
* [指定したブランチをファイルに出力する](#export-a-branch-with-history-to-a-file)
* [バンドルからインポートする](#import-from-a-bundle)
* [現在のブランチ名を表示する](#get-the-name-of-current-branch)
* [コミット時に特定の1ファイルだけ無視する (e.g. Changelog).](#ignore-one-file-on-commit-eg-changelog)
* [rebaseする前にstashする](#stash-changes-before-rebasing)
* [プルリクエストをID指定でローカルブランチにfetchする](#fetch-pull-request-by-id-to-a-local-branch)
* [現在のブランチの一番直近のタグを表示する](#show-the-most-recent-tag-on-the-current-branch)
* [単語単位のdiffを表示する](#show-inline-word-diff)
* [一般的なdiffツールで変更を表示する](#show-changes-using-common-diff-tools)
* [git管理しているファイルの変更を無視する](#dont-consider-changes-for-tracked-file)
* [assume-unchangedを無効にする](#undo-assume-unchanged)
* [`.gitignore`記載があるファイルを削除する](#clean-the-files-from-gitignore)
* [削除したファイルを元に戻す](#restore-deleted-file)
* [特定のコミットハッシュまでファイルを戻す](#restore-file-to-a-specific-commit-hash)
* [pullしたときにmergeではなくrebaseするよう変更する](#always-rebase-instead-of-merge-on-pull)
* [全てのコンフィグとエイリアスの一覧を表示する](#list-all-the-alias-and-configs)
* [ファイル名の大文字小文字変更を検知するように変更する](#make-git-case-sensitive)
* [カスタムエディターを追加する](#add-custom-editors)
* [誤字を自動修正する](#auto-correct-typos)
* [指定のハッシュが、どのブランチにいるかを表示する](#check-if-the-change-was-a-part-of-a-release)
* [ドライラン(ドライランをサポートしているコマンドに対して実行できる)](#dry-run-any-command-that-supports-dry-run-flag-should-do)
* [コミットを前回のコミットの修正としてマークする](#marks-your-commit-as-a-fix-of-a-previous-commit)
* [rebase時に上記のコミット順を隣に並べ替えてわかりやすくする](#squash-fixup-commits-normal-commits)
* [指定したファイルだけコミットする](#skip-staging-area-during-commit)
* [インタラクティブにステージングする](#interactive-staging)
* [gitが無視しているファイルを表示する](#list-ignored-files)
* [gitが無視しているファイルのステータスを表示する](#status-of-ignored-files)
* [Branch1には入っていて、Branch2に入っていないコミットを表示する](#commits-in-branch1-that-are-not-in-branch2)
* [直近n個のコミットログを表示する](#list-n-last-commits)
* [コンフリクトの解決法を記録してお、今後同じ理由でのコンフリクトが見つかったら同じ方法で自動的に解決する](#reuse-recorded-resolution-record-and-reuse-previous-conflicts-resolutions)
* [コンフリクトしたファイルをエディタで開く](#open-all-conflicted-files-in-an-editor)
* [現在のプロジェクトが使用しているオブジェクト数とディスク使用量を表示する](#count-unpacked-number-of-objects-and-their-disk-consumption)
* [到達不能オブジェクトを削除する](#prune-all-unreachable-objects-from-the-object-database)
* [作業リポジトリを gitwebで一時的にブラウジングする](#instantly-browse-your-working-repository-in-gitweb)
* [コミットログで署名も表示する](#view-the-gpg-signatures-in-the-commit-log)
* [グローバル設定を削除する](#remove-entry-in-the-global-config)
* [履歴を持たない新しい空ブランチを作成する](#checkout-a-new-branch-without-any-history)
* [別ブランチのファイルを表示する](#extract-file-from-another-branch)
* [ルートとマージコミットのみ表示する](#list-only-the-root-and-merge-commits)
* [直前の2コミットをインタラクティブにrebaseする](#change-previous-two-commits-with-an-interactive-rebase)
* [作業中のブランチを表示する](#list-all-branch-is-wip)
* [二分探索でバグの発生元を発見する](#find-guilty-with-binary-search)
* [pre-commitフックが仕掛けられているときに、チェックをスルーしてコミットする](#bypass-pre-commit-and-commit-msg-githooks)
* [特定のファイルの変更履歴を表示する (リネームされていても)](#list-commits-and-changes-to-a-specific-file-even-through-renaming)
* [特定のブランチをクローンする](#clone-a-single-branch)
* [新しいブランチを作って移動する](#create-and-switch-new-branch)
* [コミット時にファイルモードの変更を無視する](#ignore-file-mode-changes-on-commits)
* [ターミナルの出力に色を付けない](#turn-off-git-colored-terminal-output)
* [ターミナルの出力の色設定を個別に変更する](#specific-color-settings)
* [ローカルブランチを新しい順に表示する](#show-all-local-branches-ordered-by-recent-commits)
* [文字列か正規表現でgit管理下のファイルの行を検索する](#find-lines-matching-the-pattern-regex-or-string-in-tracked-files)
* [最新のリポジトリだけcloneする](#clone-a-shallow-copy-of-a-repository)
* [指定の文字で全てのブランチのコミットログを検索する](#search-commit-log-across-all-branches-for-given-text)
* [masterから指定のブランチに向けての最初のコミットを表示する](#get-first-commit-in-a-branch-from-master)
* [ステージングしたファイルをステージングする前に戻す](#unstaging-staged-file)
* [リモートリポジトリに強制的にpushする](#force-push-to-remote-repository)
* [リモートリポジトリを追加する](#adding-remote-name)
* [ファイルの全行に対して、最終更新日と更新者を表示する](#show-the-author-time-and-last-revision-made-to-each-line-of-a-given-file)
* [ユーザ毎のコミット回数とメッセージを一覧表示する](#group-commits-by-authors-and-title)
* [誰かの作業を上書きしない場合、リモートに強制的にpushする](#forced-push-but-still-ensure-you-dont-overwrite-others-work)
* [ユーザが貢献した行数を表示する](#show-how-many-lines-does-an-author-contribute)
* [リバート:全てのマージをリバートする](#revert-reverting-an-entire-merge)
* [ブランチのコミット回数を表示する](#number-of-commits-in-a-branch)
* [エイリアス: git undo](#alias-git-undo)
* [オブジェクトノートを追加する](#add-object-notes)
* [全てのオブジェクトノートを表示する](#show-all-the-git-notes)
* [別のリポジトリからコミットを適用する](#apply-commit-from-another-repository)
* [特定のリモートブランチからfetchする](#specific-fetch-reference)
* [2ブランチから共通の祖先を見付ける](#find-common-ancestor-of-two-branches)
* [pushしてないコミットを表示する](#list-unpushed-git-commits)
* [空白以外の変更をapplyする](#add-everything-but-whitespace-changes)
* [ローカル/グローバルのgitコンフィグを編集する](#edit-localglobal-git-config)
* [指定範囲内をblameする](#blame-on-certain-range)
* [git変数を表示する](#show-a-git-logical-variable)
* [整形済みのパッチを作成する](#preformatted-patch-file)
* [リポジトリのルート絶対パスを取得する](#get-the-repo-name)
* [特定期間のログを表示する](#logs-between-date-range)
* [指定者以外のログを表示する](#exclude-author-from-logs)
* [ペンディング中の変更のまとめを作成](#generates-a-summary-of-pending-changes)
* [リモートリポジトリのブランチを表示する](#list-references-in-a-remote-repository)
* [git管理していないファイルをバックアップする](#backup-untracked-files)
* [エイリアスを一覧表示する](#list-all-git-aliases)
* [git statusを簡潔に表示する](#show-git-status-short)
* [昨日のコミットをチェックアウトする](#checkout-a-commit-prior-to-a-day-ago)
* [ローカルブランチをリモートリポジトリにpushして追跡する](#push-a-new-local-branch-to-remote-repository-and-track)
* [ブランチのベースを変更する](#change-a-branch-base)
* [HTTPsではなくSSHをリモートへの接続に使用する](#use-ssh-instead-of-https-for-remotes)

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

## List of all files till a commit
```sh
git ls-tree --name-only -r <commit-ish>
```

## Git reset first commit
```sh
git update-ref -d HEAD
```

## List all the conflicted files
```sh
git diff --name-only --diff-filter=U
```

## List of all files changed in a commit
```sh
git diff-tree --no-commit-id --name-only -r <commit-ish>
```

## Unstaged changes since last commit
```sh
git diff
```

## Changes staged for commit
```sh
git diff --cached
```


__Alternatives:__
```sh
git diff --staged
```

## Show both staged and unstaged changes
```sh
git diff HEAD
```

## List all branches that are already merged into master
```sh
git branch --merged master
```

## Quickly switch to the previous branch
```sh
git checkout -
```


__Alternatives:__
```sh
git checkout @{-1}
```

## Remove branches that have already been merged with master
```sh
git branch --merged master | grep -v '^\*' | xargs -n 1 git branch -d
```


__Alternatives:__
```sh
git branch --merged master | grep -v '^\*\|  master' | xargs -n 1 git branch -d # will not delete master if master is not checked out
```

## List all branches and their upstreams, as well as last commit on branch
```sh
git branch -vv
```

## Track upstream branch
```sh
git branch -u origin/mybranch
```

## Delete local branch
```sh
git branch -d <local_branchname>
```

## Delete remote branch
```sh
git push origin --delete <remote_branchname>
```


__Alternatives:__
```sh
git push origin :<remote_branchname>
```

## Delete local tag
```sh
git tag -d <tag-name>
```

## Delete remote tag
```sh
git push origin :refs/tags/<tag-name>
```

## Undo local changes with the last content in head
```sh
git checkout -- <file_name>
```

## Revert: Undo a commit by creating a new commit
```sh
git revert <commit-ish>
```

## Reset: Discard commits, advised for private branch
```sh
git reset <commit-ish>
```

## Reword the previous commit message
```sh
git commit -v --amend
```

## See commit history for just the current branch
```sh
git cherry -v master
```

## Amend author.
```sh
git commit --amend --author='Author Name <email@address.com>'
```

## Reset author, after author has been changed in the global config.
```sh
git commit --amend --reset-author --no-edit
```

## Changing a remote's URL
```sh
git remote set-url origin <URL>
```

## Get list of all remote references
```sh
git remote
```


__Alternatives:__
```sh
git remote show
```

## Get list of all local and remote branches
```sh
git branch -a
```

## Get only remote branches
```sh
git branch -r
```

## Stage parts of a changed file, instead of the entire file
```sh
git add -p
```

## Get git bash completion
```sh
curl -L http://git.io/vfhol > ~/.git-completion.bash && echo '[ -f ~/.git-completion.bash ] && . ~/.git-completion.bash' >> ~/.bashrc
```

## What changed since two weeks?
```sh
git log --no-merges --raw --since='2 weeks ago'
```


__Alternatives:__
```sh
git whatchanged --since='2 weeks ago'
```

## See all commits made since forking from master
```sh
git log --no-merges --stat --reverse master..
```

## Pick commits across branches using cherry-pick
```sh
git checkout <branch-name> && git cherry-pick <commit-ish>
```

## Find out branches containing commit-hash
```sh
git branch -a --contains <commit-ish>
```


__Alternatives:__
```sh
git branch --contains <commit-ish>
```

## Git Aliases
```sh
git config --global alias.<handle> <command> 
git config --global alias.st status
```

## Saving current state of tracked files without commiting
```sh
git stash
```


__Alternatives:__
```sh
git stash save
```

## Saving current state of unstaged changes to tracked files
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

## Saving current state including untracked files
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

## Saving current state with message
```sh
git stash save <message>
```

## Saving current state of all files (ignored, untracked, and tracked)
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

## Show list of all saved stashes
```sh
git stash list
```

## Apply any stash without deleting from the stashed list
```sh
git stash apply <stash@{n}>
```

## Apply last stashed state and delete it from stashed list
```sh
git stash pop
```


__Alternatives:__
```sh
git stash apply stash@{0} && git stash drop stash@{0}
```

## Delete all stored stashes
```sh
git stash clear
```


__Alternatives:__
```sh
git stash drop <stash@{n}>
```

## Grab a single file from a stash
```sh
git checkout <stash@{n}> -- <file_path>
```


__Alternatives:__
```sh
git checkout stash@{0} -- <file_path>
```

## Show all tracked files
```sh
git ls-files -t
```

## Show all untracked files
```sh
git ls-files --others
```

## Show all ignored files
```sh
git ls-files --others -i --exclude-standard
```

## Create new working tree from a repository (git 2.5)
```sh
git worktree add -b <branch-name> <path> <start-point>
```

## Create new working tree from HEAD state
```sh
git worktree add --detach <path> HEAD
```

## Untrack files without deleting
```sh
git rm --cached <file_path>
```


__Alternatives:__
```sh
git rm --cached -r <directory_path>
```

## Before deleting untracked files/directory, do a dry run to get the list of these files/directories
```sh
git clean -n
```

## Forcefully remove untracked files
```sh
git clean -f
```

## Forcefully remove untracked directory
```sh
git clean -f -d
```

## Update all the submodules
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

## Show all commits in the current branch yet to be merged to master
```sh
git cherry -v master
```


__Alternatives:__
```sh
git cherry -v master <branch-to-be-merged>
```

## Rename a branch
```sh
git branch -m <new-branch-name>
```


__Alternatives:__
```sh
git branch -m [<old-branch-name>] <new-branch-name>
```

## Rebases 'feature' to 'master' and merges it in to master 
```sh
git rebase master feature && git checkout master && git merge -
```

## Archive the `master` branch
```sh
git archive master --format=zip --output=master.zip
```

## Modify previous commit without modifying the commit message
```sh
git add --all && git commit --amend --no-edit
```

## Prunes references to remote branches that have been deleted in the remote.
```sh
git fetch -p
```


__Alternatives:__
```sh
git remote prune origin
```

## Retrieve the commit hash of the initial revision.
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

## Visualize the version tree.
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

## Visualize the tree including commits that are only referenced from reflogs
```sh
git log --graph --decorate --oneline $(git rev-list --walk-reflogs --all)
```

## Deploying git tracked subfolder to gh-pages
```sh
git subtree push --prefix subfolder_name origin gh-pages
```

## Adding a project to repo using subtree
```sh
git subtree add --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## Get latest changes in your repo for a linked project using subtree
```sh
git subtree pull --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## Export a branch with history to a file.
```sh
git bundle create <file> <branch-name>
```

## Import from a bundle
```sh
git clone repo.bundle <repo-dir> -b <branch-name>
```

## Get the name of current branch.
```sh
git rev-parse --abbrev-ref HEAD
```

## Ignore one file on commit (e.g. Changelog).
```sh
git update-index --assume-unchanged Changelog; git commit -a; git update-index --no-assume-unchanged Changelog
```

## Stash changes before rebasing
```sh
git rebase --autostash
```

## Fetch pull request by ID to a local branch
```sh
git fetch origin pull/<id>/head:<branch-name>
```


__Alternatives:__
```sh
git pull origin pull/<id>/head:<branch-name>
```

## Show the most recent tag on the current branch.
```sh
git describe --tags --abbrev=0
```

## Show inline word diff.
```sh
git diff --word-diff
```

## Show changes using common diff tools.
```sh
git difftool [-t <tool>] <commit1> <commit2> <path>
```

## Don’t consider changes for tracked file.
```sh
git update-index --assume-unchanged <file_name>
```

## Undo assume-unchanged.
```sh
git update-index --no-assume-unchanged <file_name>
```

## Clean the files from `.gitignore`.
```sh
git clean -X -f
```

## Restore deleted file.
```sh
git checkout <deleting_commit>^ -- <file_path>
```

## Restore file to a specific commit-hash
```sh
git checkout <commit-ish> -- <file_path>
```

## Always rebase instead of merge on pull.
```sh
git config --global pull.rebase true
```


__Alternatives:__
```sh
#git < 1.7.9
git config --global branch.autosetuprebase always
```

## List all the alias and configs.
```sh
git config --list
```

## Make git case sensitive.
```sh
git config --global core.ignorecase false
```

## Add custom editors.
```sh
git config --global core.editor '$EDITOR'
```

## Auto correct typos.
```sh
git config --global help.autocorrect 1
```

## Check if the change was a part of a release.
```sh
git name-rev --name-only <SHA-1>
```

## Dry run. (any command that supports dry-run flag should do.)
```sh
git clean -fd --dry-run
```

## Marks your commit as a fix of a previous commit.
```sh
git commit --fixup <SHA-1>
```

## Squash fixup commits normal commits.
```sh
git rebase -i --autosquash
```

## Skip staging area during commit.
```sh
git commit --only <file_path>
```

## Interactive staging.
```sh
git add -i
```

## List ignored files.
```sh
git check-ignore *
```

## Status of ignored files.
```sh
git status --ignored
```

## Commits in Branch1 that are not in Branch2
```sh
git log Branch1 ^Branch2
```

## List n last commits
```sh
git log -<n>
```


__Alternatives:__
```sh
git log -n <n>
```

## Reuse recorded resolution, record and reuse previous conflicts resolutions.
```sh
git config --global rerere.enabled 1
```

## Open all conflicted files in an editor.
```sh
git diff --name-only | uniq | xargs $EDITOR
```

## Count unpacked number of objects and their disk consumption.
```sh
git count-objects --human-readable
```

## Prune all unreachable objects from the object database.
```sh
git gc --prune=now --aggressive
```

## Instantly browse your working repository in gitweb.
```sh
git instaweb [--local] [--httpd=<httpd>] [--port=<port>] [--browser=<browser>]
```

## View the GPG signatures in the commit log
```sh
git log --show-signature
```

## Remove entry in the global config.
```sh
git config --global --unset <entry-name>
```

## Checkout a new branch without any history
```sh
git checkout --orphan <branch_name>
```

## Extract file from another branch.
```sh
git show <branch_name>:<file_name>
```

## List only the root and merge commits.
```sh
git log --first-parent
```

## Change previous two commits with an interactive rebase.
```sh
git rebase --interactive HEAD~2
```

## List all branch is WIP
```sh
git checkout master && git branch --no-merged
```

## Find guilty with binary search
```sh
git bisect start                    # Search start 
git bisect bad                      # Set point to bad commit 
git bisect good v2.6.13-rc2         # Set point to good commit|tag 
git bisect bad                      # Say current state is bad 
git bisect good                     # Say current state is good 
git bisect reset                    # Finish search 

```

## Bypass pre-commit and commit-msg githooks
```sh
git commit --no-verify
```

## List commits and changes to a specific file (even through renaming)
```sh
git log --follow -p -- <file_path>
```

## Clone a single branch
```sh
git clone -b <branch-name> --single-branch https://github.com/user/repo.git
```

## Create and switch new branch
```sh
git checkout -b <branch-name>
```


__Alternatives:__
```sh
git branch <branch-name> && git checkout <branch-name>
```

## Ignore file mode changes on commits
```sh
git config core.fileMode false
```

## Turn off git colored terminal output
```sh
git config --global color.ui false
```

## Specific color settings
```sh
git config --global <specific command e.g branch, diff> <true, false or always>
```

## Show all local branches ordered by recent commits
```sh
git for-each-ref --sort=-committerdate --format='%(refname:short)' refs/heads/
```

## Find lines matching the pattern (regex or string) in tracked files
```sh
git grep --heading --line-number 'foo bar'
```

## Clone a shallow copy of a repository
```sh
git clone https://github.com/user/repo.git --depth 1
```

## Search Commit log across all branches for given text
```sh
git log --all --grep='<given-text>'
```

## Get first commit in a branch (from master)
```sh
git log --oneline master..<branch-name> | tail -1
```


__Alternatives:__
```sh
git log --reverse master..<branch-name> | head -6
```

## Unstaging Staged file
```sh
git reset HEAD <file-name>
```

## Force push to Remote Repository
```sh
git push -f <remote-name> <branch-name>
```

## Adding Remote name
```sh
git remote add <remote-nickname> <remote-url>
```

## Show the author, time and last revision made to each line of a given file
```sh
git blame <file-name>
```

## Group commits by authors and title
```sh
git shortlog
```

## Forced push but still ensure you don't overwrite other's work
```sh
git push --force-with-lease <remote-name> <branch-name>
```

## Show how many lines does an author contribute
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | gawk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s removed lines: %s total lines: %s
", add, subs, loc }' -
```


__Alternatives:__
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | awk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s, removed lines: %s, total lines: %s
", add, subs, loc }' - # on Mac OSX
```

## Revert: Reverting an entire merge
```sh
git revert -m 1 <commit-ish>
```

## Number of commits in a branch
```sh
git rev-list --count <branch-name>
```

## Alias: git undo
```sh
git config --global alias.undo '!f() { git reset --hard $(git rev-parse --abbrev-ref HEAD)@{${1-1}}; }; f'
```

## Add object notes
```sh
git notes add -m 'Note on the previous commit....'
```

## Show all the git-notes
```sh
git log --show-notes='*'
```

## Apply commit from another repository
```sh
git --git-dir=<source-dir>/.git format-patch -k -1 --stdout <SHA1> | git am -3 -k
```

## Specific fetch reference
```sh
git fetch origin master:refs/remotes/origin/mymaster
```

## Find common ancestor of two branches
```sh
diff -u <(git rev-list --first-parent BranchA) <(git rev-list --first-parent BranchB) | sed -ne 's/^ //p' | head -1
```

## List unpushed git commits
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

## Add everything, but whitespace changes
```sh
git diff --ignore-all-space | git apply --cached
```

## Edit [local/global] git config
```sh
git config [--global] --edit
```

## blame on certain range
```sh
git blame -L <start>,<end>
```

## Show a Git logical variable.
```sh
git var -l | <variable>
```

## Preformatted patch file.
```sh
git format-patch -M upstream..topic
```

## Get the repo name.
```sh
git rev-parse --show-toplevel
```

## logs between date range
```sh
git log --since='FEB 1 2017' --until='FEB 14 2017'
```

## Exclude author from logs
```sh
git log --perl-regexp --author='^((?!excluded-author-regex).*)

```

## Generates a summary of pending changes
```sh
git request-pull v1.0 https://git.ko.xz/project master:for-linus
```

## List references in a remote repository
```sh
git ls-remote git://git.kernel.org/pub/scm/git/git.git
```

## Backup untracked files.
```sh
git ls-files --others -i --exclude-standard | xargs zip untracked.zip
```

## List all git aliases
```sh
git config -l | grep alias | sed 's/^alias\.//g'
```


__Alternatives:__
```sh
git config -l | grep alias | cut -d '.' -f 2
```

## Show git status short
```sh
git status --short --branch
```

## Checkout a commit prior to a day ago
```sh
git checkout master@{yesterday}
```

## Push a new local branch to remote repository and track
```sh
git push -u origin <branch_name>
```

## Change a branch base
```sh
git rebase --onto <new_base> <old_base>
```

## Use SSH instead of HTTPs for remotes
```sh
git config --global url.'git@github.com:'.insteadOf 'https://github.com/'
```

<!-- Don’t remove or change the comment below – that can break automatic updates. More info at <http://npm.im/doxie.inject>. -->
<!-- @doxie.inject end -->
