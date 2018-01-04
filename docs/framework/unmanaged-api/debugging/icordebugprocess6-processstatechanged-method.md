---
title: "ICorDebugProcess6::ProcessStateChanged 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e5aad3e95668525fe607bf4e90b4e05b2b58cad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6processstatechanged-method"></a>ICorDebugProcess6::ProcessStateChanged 方法
通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a>参数  
 `change`  
 [in]成员[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)枚举  
  
## <a name="remarks"></a>备注  
 调试程序调用该方法以通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)进程运行。  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugProcess6 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
