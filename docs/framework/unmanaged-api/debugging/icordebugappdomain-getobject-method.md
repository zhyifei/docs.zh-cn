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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895215"
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
 如果尚未为<xref:System.AppDomain?displayProperty=nameWithType>此应用程序域构造托管对象，则该方法将`S_FALSE`返回， `NULL`并`*ppObject`将放入。  
  
## <a name="remarks"></a>备注  
 进程中的每个应用程序域在运行<xref:System.AppDomain?displayProperty=nameWithType>时中都可能有一个表示该对象的托管对象。 此函数获取对应于此托管<xref:System.AppDomain?displayProperty=nameWithType>对象的 ICorDebugValue 接口对象。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
