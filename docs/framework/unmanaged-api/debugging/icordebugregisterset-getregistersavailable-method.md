---
title: ICorDebugRegisterSet::GetRegistersAvailable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f341098268f735a576bdbc5f0cea52f1a7e14f90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782903"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>ICorDebugRegisterSet::GetRegistersAvailable 메서드
가져옵니다가 등록을 나타내는 비트 마스크 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 현재 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pAvailable`  
 [out] 현재 사용할 수 있는 레지스터가 있는 여부를 나타내는 비트 마스크입니다.  
  
## <a name="remarks"></a>설명  
 레지스터 주어진된 상황에 대 한 해당 값을 확인할 수 없는 경우 사용할 수 있습니다.  
  
 반환 된 마스크 각 등록에 대 한 하나의 비트가 포함 (1 << 등록 인덱스). 비트 값이 1 이면 레지스터를 사용할 수 또는 사용할 수 없는 경우 0입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
