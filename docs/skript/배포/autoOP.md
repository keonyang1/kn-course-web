# **autoOP**

```vb
# ============================================================================================== #
# Skript Name: AutoOP
# Author: 커냥 (keonyang1)
# Discord: keonyang1
# Date: 2025-06-08
# Description: 서버에 접속하면 자동으로 OP를 부여받고, 명령어로도 OP를 얻을 수 있는 스크립트입니다.
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
    AutoOP: &7[&9AutoOP&7] &f

# 첫 접속 시 도움말
on first join:
    send "{@AutoOP}이 서버에서는 &a/getop &f명령어를 사용하여 오피(op)를 얻으실 수 있습니다"
    send "{@AutoOP}기본적으로 접속 시 오피(op)가 지급되며, 실수 혹은 테스트 등의 이유로 오피(op)를 잃으셔도 위의 명령어를 사용하시면 됩니다"
    send "{@AutoOP}(위의 내용은 &a/도움말 &f명령어를 사용하여 다시 확인하실 수 있습니다)"
    op player

# 접속 시 도움말
on join:
    send "{@AutoOP}도움이 필요하시면 &a/도움말 &f명령어를 사용해 보세요!"

# 도움말
command /도움말:
    trigger:
        send "{@AutoOP}이 서버에서는 &a/getop &f명령어를 사용하여 오피(op)를 얻으실 수 있습니다"
        send "{@AutoOP}기본적으로 접속 시 오피(op)가 지급되며, 실수 혹은 테스트 등의 이유로 오피(op)를 잃으셔도 위의 명령어를 사용하시면 됩니다"

# getop
command /getop:
    trigger:
        send "{@AutoOP}&b오피(op)가 지급되었습니다"
        op player
```
