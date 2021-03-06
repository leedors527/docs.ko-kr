---
title: ICorDebugMutableDataTarget::WriteVirtual 메서드
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fba970de6e5882d3cbe9be17b5b49be5a3e81aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927376"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a>ICorDebugMutableDataTarget::WriteVirtual 메서드
대상 프로세스 주소 공간에 메모리를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 [in] `pBuffer`의 콘텐츠를 쓸 주소입니다.  
  
 `pBuffer`  
 [in] 쓸 바이트를 포함하는 바이트 배열에 대한 포인터입니다.  
  
 `address`  
 [in] `pBuffer`의 바이트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `S_OK`이고 실패하면 다른 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 바이트를 쓸 수 없는 경우 대상 주소 공간의 바이트를 변경하지 않고 메서드 호출이 실패합니다. 그러지 않으면 대상이 일관성 없는 상태가 되어 이후 디버깅을 신뢰할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugMutableDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
