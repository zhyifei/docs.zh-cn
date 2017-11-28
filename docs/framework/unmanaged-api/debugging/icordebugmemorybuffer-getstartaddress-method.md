---
title: "ICorDebugMemoryBuffer::GetStartAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97c08e87f63b36bfee5ade75e44f4867441bee92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>ICorDebugMemoryBuffer::GetStartAddress 方法
获取内存缓冲区的起始地址。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a>参数  
 `address`  
 [out] 指向内存缓冲区起始地址的指针。  
  
## <a name="remarks"></a>备注  
  
> [!WARNING]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugMemoryBuffer 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
