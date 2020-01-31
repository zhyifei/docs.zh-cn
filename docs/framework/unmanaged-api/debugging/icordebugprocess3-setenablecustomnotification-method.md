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
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792467"
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
 将 `fEnable` 设置为 `true`时，对 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 方法的调用会触发[ICorDebugManagedCallback3：： CustomNotification](icordebugmanagedcallback3-customnotification-method.md)回调。 默认情况下禁用通知;因此，调试器必须指定它知道的任何通知类型并想要处理。 由于[ICorDebugClass](icordebug-interface.md)类的作用域由应用程序域确定，因此，如果要在整个过程中接收通知，则调试器必须为进程中的每个应用程序域调用 `SetEnableCustomNotification`。  
  
 从 .NET Framework 4 开始，唯一受支持的通知是跨线程依赖项通知。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugProcess3 接口](icordebugprocess3-interface.md)
- [调试接口](debugging-interfaces.md)
- [调试](index.md)
