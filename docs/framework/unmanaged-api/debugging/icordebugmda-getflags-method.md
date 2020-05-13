---
title: ICorDebugMDA::GetFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 4e5939e9e74899a33f28927c4fda09d0a8fb30a0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209729"
---
# <a name="icordebugmdagetflags-method"></a>ICorDebugMDA::GetFlags 方法
获取与[ICorDebugMDA](icordebugmda-interface.md)表示的托管调试助手（MDA）关联的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `pFlags`  
 中[CorDebugMDAFlags](cordebugmdaflags-enumeration.md)枚举值的按位组合，这些值指定此 MDA 的标志的设置。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMDA 接口](icordebugmda-interface.md)
- [使用托管调试助手诊断错误](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
