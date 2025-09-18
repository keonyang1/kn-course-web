# **motd**

```vb
# ============================================================================================== #
# Skript Name: Motd
# Author: 커냥 (keonyang1)
# Discord: keonyang1
# Date: 2025-06-08
# Description: 서버 리스트에 뜨는 motd문구를 설정하는 스크립트입니다.
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
    # 첫번째 줄
    line1: &6☾ =============&c<&6<&e< &b놀이터 서버 &e>&6>&c>&6============= ☽

    # 두번째 줄
    line2: &e &b ˚✧₊⁎ &e건축, 커맨드, 회로 &5  version: &3[1.21.4]&b ⁎⁺˳✧˚

# motd띄우기
on server list ping:
    set motd to "{@line1}%nl%{@line2}"
```
