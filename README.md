# サラタメさん 音声版

YouTube「サラタメさん」（@salatame）の本解説動画を音声化し、Apple Podcasts で聴けるようにする仕組み。
構成は `~/claude/icu-talk-podcast` と同じ（取得は Mac、配信は GitHub Pages）。

## スマホで聴く
- フィード: https://wtkn1140-collab.github.io/saratame-podcast/feed.xml
  （Apple Podcasts → ライブラリ →「…」→「URLで番組をフォロー」）
- プレーヤー: https://wtkn1140-collab.github.io/saratame-podcast/

## Mac 側
- 自動実行: `~/Library/LaunchAgents/com.saratame.podcast.plist` → `run.sh`（2時間ごと）
- ログ: `logs/update.log`
- 手動で今すぐ取得: `./run.sh`
- 自動実行を止める: `launchctl bootout gui/$(id -u) ~/Library/LaunchAgents/com.saratame.podcast.plist`
- 最新15本は `audio-site/`（saratame-podcast-audio）、それより前（最新100本まで）は `archive1/`〜（saratame-podcast-archiveN）
- 題名は英訳が返ってくるため `youtube:lang=ja` で日本語を取得している
