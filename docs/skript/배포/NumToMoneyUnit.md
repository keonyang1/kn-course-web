# **NumToMoneyUnit**

```vb
# ============================================================================================== #
# Skript Name: [Module] NumToMoneyUnit
# Author: 커냥 (keonyang1)
# Discord: keonyang1
# Date: 2025-06-08
# Description: 숫자를 통화로 변환하는 스크립트입니다.
# Copyright (c) 2025 커냥(keonyang1). All rights reserved.
# License: All rights reserved
# 사용 허가 없이 재배포, 수정, 상업적 이용 금지
# ============================================================================================== #

# 숫자를 통화로 변환
function NumToMoneyUnit(n:number) :: text:
    # 입력값을 정수 부분과 소수 부분으로 분리
    set {_integerPart} to floor({_n})
    set {_decimalSplit::*} to "%{_n}%" split at "."
    set {_decimalPart} to {_decimalSplit::2} if size of {_decimalSplit::*} > 1
    
    # 정수 부분을 쉼표로 구분된 형식으로 변환
    set {_r} to "%{_integerPart}%"
    set {_t} to ""
    loop round up length of {_r} / 3 times:
        set {_l} to the last 3 characters of {_r}
        set {_r} to the first length of {_r} - 3 characters of {_r}
        if loop-number = 1:
            set {_t} to "%{_l}%%{_t}%"
        else:
            set {_t} to "%{_l}%,%{_t}%"
    
    # 소수 부분을 포함한 결과 반환
    if {_decimalPart} is set:
        return "%{_t}%.%{_decimalPart}%"
    else:
        return "%{_t}%"
```
