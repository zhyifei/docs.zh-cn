---
title: ICorDebug::Terminate 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 2d3f8360a1fb1164fd4e26f85246251409bee376
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788950"
---
# <a name="icordebugterminate-method"></a>ICorDebug::Terminate 方法
终止 `ICorDebug` 的对象。  
  
> [!NOTE]
> 在为所有正在调试的进程接收到[ICorDebugManagedCallback：： ExitProcess](icordebugmanagedcallback-exitprocess-method.md)回调之前，不应调用 `Terminate`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>备注  
 当不再需要 `ICorDebug` 对象时，必须调用 `Terminate`。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebug 接口](icordebug-interface.md)
