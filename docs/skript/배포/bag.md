# **bag**

```vb
# ============================================================================================== #
# Skript Name: Bag
# Author: 커냥 (keonyang1)
# Discord: keonyang1
# Date: 2025-06-08
# Description: 플레이어마다 아이템을 저장할 수 있는 가방을 만들어주는 스크립트입니다.
# Copyright (c) 2025 커냥(keonyang1). All rights reserved.
# License: All rights reserved
# 사용 허가 없이 재배포, 수정, 상업적 이용 금지
# ============================================================================================== #

# 필요한 모듈
# [Module] NumToMoneyUnit

# 필요한 애드온
# -

# 옵션 설정
options:
    # 메시지 접두사
    bag: &7[&c&l가방&7] &f

    # 현재 사용중인 돈 변수
    # 기본값: {money::%uuid of player%}
    돈: {money::%uuid of player%}

    # 가방을 여는데 드는 비용
    비용: 0

    # 발생한 비용이 들어갈 변수
    # 기본값: {서버지갑}
    서버지갑: {서버지갑}

    # 서버지갑기능 사용 여부 (true/false)
    # 기본값: false
    서버지갑사용: false

    # 가방 줄 수 (1~6)
    # 큰 상자 기준으로 가로 줄 수
    # ex) 1줄 >> 9칸, 6줄 >> 54칸
    # 기본값: 3
    줄: 3

# 가방 체스트 띄우기
command /bag:
    aliases: /가방
    trigger:
        if {@비용} is not 0:
            if {@비용} > {@돈}:
                play sound "block.note_block.bass" with volume 100 and pitch 0.7 to player
                send "{@bag}&c돈이 부족합니다"
                stop
            else:
                play sound "block.decorated_pot.insert" with volume 100 and pitch 1.7 to player
                send "{@bag}&a가방을 열었습니다 &e(비용: %NumToMoneyUnit({@비용})%원)"
                remove {@비용} from {@돈}
                if {@서버지갑사용} is true:
                    add {@비용} to {@서버지갑}
        open chest inventory with {@줄} row named "&c&l가방" to player
        loop {bag.%uuid of player%::*}:
            set {_slot} to loop-index parsed as number
            set slot {_slot} of current inventory of player to loop-value

# 아이템 정보 저장
on inventory close:
    if icname is "&c&l가방":
        loop {@line}*9 times:
            set {bag.%uuid of player%::%{_idx}%} to slot (loop-value - 1) of current inventory of player
```
