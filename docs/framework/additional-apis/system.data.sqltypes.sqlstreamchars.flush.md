---
title: SqlStreamChars.Flush 메서드 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8cd24a5ca420552f283da61ecd4edcad02965403
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705859"
---
# <a name="sqlstreamcharsflush-method"></a>SqlStreamChars.Flush 메서드

파생 클래스에서 재정의되면 이 스트림에 대해 모든 버퍼를 지우고 버퍼링된 데이터가 내부 장치에 쓰여지도록 합니다. 이 메서드를 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다. SQL Server에서 사용할 것입니다. 다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.

## <a name="syntax"></a>구문

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a>설명

> [!WARNING]
> `SqlStreamChars.Flush` 메서드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.
>
> Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Data.SqlTypes>

**어셈블리:** System.Data (System.Data.dll)

**.NET framework 버전:** 2.0부터 사용할 수 있습니다.