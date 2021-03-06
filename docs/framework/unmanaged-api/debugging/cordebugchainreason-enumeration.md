---
title: CorDebugChainReason 열거형
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cac790ebbf25ee3095db293ba90612be37fff9b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609232"
---
# <a name="cordebugchainreason-enumeration"></a>CorDebugChainReason 열거형
호출 체인의 시작 이유를 하나 이상 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`CHAIN_NONE`|호출 체인이 시작되지 않았습니다.|  
|`CHAIN_CLASS_INIT`|생성자를 통해 체인이 시작되었습니다.|  
|`CHAIN_EXCEPTION_FILTER`|예외 필터를 통해 체인이 시작되었습니다.|  
|`CHAIN_SECURITY`|보안을 적용하는 코드를 통해 체인이 시작되었습니다.|  
|`CHAIN_CONTEXT_POLICY`|컨텍스트 정책을 통해 체인이 시작되었습니다.|  
|`CHAIN_INTERCEPTION`|사용되지 않습니다.|  
|`CHAIN_PROCESS_START`|사용되지 않습니다.|  
|`CHAIN_THREAD_START`|스레드 실행 시작을 통해 체인이 시작되었습니다.|  
|`CHAIN_ENTER_MANAGED`|관리 코드에 대한 입력을 통해 체인이 시작되었습니다.|  
|`CHAIN_ENTER_UNMANAGED`|비관리 코드에 대한 입력을 통해 체인이 시작되었습니다.|  
|`CHAIN_DEBUGGER_EVAL`|사용되지 않습니다.|  
|`CHAIN_CONTEXT_SWITCH`|사용되지 않습니다.|  
|`CHAIN_FUNC_EVAL`|함수 평가를 통해 체인이 시작되었습니다.|  
  
## <a name="remarks"></a>설명  
 사용 된 [icordebugchain:: Getreason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) 호출 체인의 시작에 대 한 이유를 확인 하는 방법입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
