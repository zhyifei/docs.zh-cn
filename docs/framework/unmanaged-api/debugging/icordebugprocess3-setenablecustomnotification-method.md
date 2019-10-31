---
title: ICorDebugProcess3::SetEnableCustomNotification 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: ec60274648315c4fa38f3832d8d39c1a269956b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129707"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification 方法
启用和禁用指定类型的自定义调试器通知。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>参数  
 `pClass`  
 中指定自定义调试器通知的类型。  
  
 `fEnable`  
 [in] 用于启用自定义调试器通知的 `true`;`false` 禁用通知。 默认值为 `false`。  
  
## <a name="remarks"></a>备注  
 将 `fEnable` 设置为 `true`时，对 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 方法的调用会触发[ICorDebugManagedCallback3：： CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)回调。 默认情况下禁用通知;因此，调试器必须指定它知道的任何通知类型并想要处理。 由于[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)类的作用域由应用程序域确定，因此，如果要在整个过程中接收通知，则调试器必须为进程中的每个应用程序域调用 `SetEnableCustomNotification`。  
  
 从 .NET Framework 4 开始，唯一受支持的通知是跨线程依赖项通知。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugProcess3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
