# **default-item(iron)**

```vb
# ============================================================================================== #
# Skript Name: Default Item
# Author: 커냥 (keonyang1)
# Discord: keonyang1
# Date: 2025-06-08
# Description: 철 갑옷, 도구 등의 1회성 기본템을 지급해주는 스크립트입니다.
# Copyright (c) 2025 커냥(keonyang1). All rights reserved.
# License: All rights reserved
# 사용 허가 없이 재배포, 수정, 상업적 이용 금지
# ============================================================================================== #

# 필요한 모듈
# -

# 필요한 애드온
# -

# 옵션 설정
options:
    # 메시지 접두사
    DI: &7[&e&l기본템&7] &f

# 기본템 지급
command /기본템:
    trigger:
        if {DI.%uuid of player%} is not set:
            set {DI.%uuid of player%} to true
            give 1 of iron sword to player
            give 1 of iron pickaxe to player
            give 1 of iron axe to player
            give 1 of iron shovel to player
            give 1 of iron hoe to player
            give 1 of iron helmet to player
            give 1 of iron chestplate to player
            give 1 of iron leggings to player
            give 1 of iron boots to player
            give 64 of cooked beef to player
            send "{@DI}&a기본템을 얻었습니다"
        else:
            send "{@DI}&c이미 기본템을 얻었습니다"

# 기본템 1회 정보 초기화
command /기본템초기화 [<player>]:
    permission: op
    trigger:
        if arg 1 is set:
            delete {DI.%uuid of arg 1%}
            send "{@DI}&b%arg 1%&f님의 기본템 데이터를 초기화되었습니다."
        else:
            send "{@DI}&b명령어 사용법&7: &f/기본템초기화 <player>"
```
