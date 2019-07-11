---
title: ICorDebugAppDomain::EnumerateBreakpoints 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a683f1531ed28fbd8ef085414bb7cb365762ffde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738037"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a>ICorDebugAppDomain::EnumerateBreakpoints 方法
获取应用程序域中所有活动断点的枚举数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppBreakpoints`  
 [out]指向一个 ICorDebugBreakpointEnum 对象，它的应用程序域中的所有活动断点的枚举器的地址的指针。  
  
## <a name="remarks"></a>备注  
 枚举器包括所有类型的断点，包括函数断点和数据断点。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
