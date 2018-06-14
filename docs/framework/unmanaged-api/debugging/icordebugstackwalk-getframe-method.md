---
title: ICorDebugStackWalk::GetFrame 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 548a8a7743c02be5734b677010627f847c5bc4b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421982"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame 方法
获取当前帧中[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
#### <a name="parameters"></a>参数  
 `pFrame`  
 [in]指向表示当前帧堆栈中的创建的框架对象的地址的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|运行时成功地返回当前帧。|  
|E_FAIL|不返回当前帧。|  
|S_FALSE|当前帧是本机的堆栈帧。|  
|E_INVALIDARG|`pFrame` 为 null。|  
|CORDBG_E_PAST_END_OF_STACK|帧指针是已在堆栈; 末尾因此，可以不访问任何其他帧。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 `ICorDebugStackWalk` 返回仅实际堆栈帧。 使用[icordebugthread3:: Getactiveinternalframes](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)方法以返回内部帧。 （内部帧是推送到堆栈由运行时存储临时数据的数据结构。）  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugStackWalk 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
