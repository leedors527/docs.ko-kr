---
title: CorDebugInternalFrameType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05184ceb3b32eb003951fff5cfdfbfb813992552
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792862"
---
# <a name="cordebuginternalframetype-enumeration"></a>CorDebugInternalFrameType 열거형
스택 프레임 형식을 식별합니다. 이 열거형은에서 사용 된 [icordebuginternalframe:: Getframetype](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`STUBFRAME_NONE`|null 값입니다. `ICorDebugInternalFrame::GetFrameType` 메서드는이 값을 반환 하지 않습니다.|  
|`STUBFRAME_M2U`|관리-비관리 스텁 프레임입니다.|  
|`STUBFRAME_U2M`|관리 되지 않는-managed 스텁 프레임입니다.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|응용 프로그램 도메인 간에 전환 합니다.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|간단한 메서드 호출입니다.|  
|`STUBFRAME_FUNC_EVAL`|함수 실행의 시작입니다.|  
|`STUBFRAME_INTERNALCALL`|공용 언어 런타임에 대 한 내부 호출 합니다.|  
|`STUBFRAME_CLASS_INIT`|클래스 초기화를 시작 합니다.|  
|`STUBFRAME_EXCEPTION`|예외가 throw 됩니다.|  
|`STUBFRAME_SECURITY`|코드 액세스 보안에 사용 되는 프레임입니다.|  
|`STUBFRAME_JIT_COMPILATION`|런타임은 메서드를 JIT 컴파일하는입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
