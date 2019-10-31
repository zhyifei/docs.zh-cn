---
title: ICorDebugAppDomain::GetObject 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134704"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject 方法
获取指向公共语言运行时（CLR）应用程序域的接口指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppObject`  
 弄指向表示 CLR 应用程序域的 ICorDebugValue 接口对象地址的指针。  
  
## <a name="return-value"></a>返回值  
 如果尚未为此应用程序域构造托管的 <xref:System.AppDomain?displayProperty=nameWithType> 对象，则该方法将返回 `S_FALSE` 并将 `NULL` 放置在 `*ppObject`中。  
  
## <a name="remarks"></a>备注  
 进程中的每个应用程序域在运行时中都可能有一个托管的 <xref:System.AppDomain?displayProperty=nameWithType> 对象。 此函数获取对应于此托管 <xref:System.AppDomain?displayProperty=nameWithType> 对象的 ICorDebugValue 接口对象。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
