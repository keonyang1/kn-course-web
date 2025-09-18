# **nightvision**

```vb
# ============================================================================================== #
# Skript Name: Nightvision
# Author: 커냥 (keonyang1)
# Discord: keonyang1
# Date: 2025-06-08
# Description: 야간투시를 켜고 끌 수 있게 해주는 스크립트입니다.
# Copyright (c) 2025 커냥(keonyang1). All rights reserved.
# License: All rights reserved
# 사용 허가 없이 재배포, 수정, 상업적 이용 금지
# ============================================================================================== #

# 필요한 모듈
# -

# 필요한 애드온
# SkBee

# 옵션 설정
options:
    # 메시지 접두사
    nightvision: &7[&a&l야간 투시&7] &f

# 야간투시 효과
command /야간투시 [<text>]:
    aliases: /nightvision, /dirksxntl
    trigger:
        if arg 1 is "on":
            apply infinite potion of night vision of tier 1 without particles to player
            send "{@nightvision}&a야간 투시 효과가 적용되었습니다"
        else if arg 1 is "off":
            remove night vision from player
            send "{@nightvision}&c야간 투시 효과가 해제되었습니다"
        else:
            send "{@nightvision}&b명령어 사용법&7: &f/야간투시 <on/off>"
# 자동완성
on tab complete of "/야간투시", "/nightvision" and "/dirksxntl":
    set tab completions for position 1 to "on" and "off"
```
