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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a84061cff7cc5dbdeba1e0e66396e04a8f345cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423151"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification 方法
启用和禁用的指定类型的自定义调试器通知。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a>参数  
 `pClass`  
 [in]指定自定义调试器通知的类型。  
  
 `fEnable`  
 [in]`true`启用自定义调试器通知;`false`禁用通知。 默认值为 `false`。  
  
## <a name="remarks"></a>备注  
 当`fEnable`设置为`true`，调用<xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>方法触发器[icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)回调。 默认情况下; 禁用通知因此，调试器必须指定它就会了解有关并想要处理的任何通知类型。 因为[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)类的作用范围由应用程序域，调试器必须调用`SetEnableCustomNotification`的每个应用程序域中的过程，如果想要在整个进程接收通知。  
  
 从开始[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，则仅支持的通知是一个跨线程依赖项通知。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugProcess3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
