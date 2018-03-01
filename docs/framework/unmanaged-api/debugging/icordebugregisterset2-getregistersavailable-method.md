---
title: "ICorDebugRegisterSet2::GetRegistersAvailable 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e2e3862f91fc68879e2f9e396ab9045c617de82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable 方法
获取提供的可用寄存器位图的字节数组。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `numChunks`  
 [in] `availableRegChunks` 数组的大小。  
  
 `availableRegChunks`  
 [out]字节数组，其中每位对应于寄存器。 如果可用的寄存器，注册的对应位将设置。  
  
## <a name="remarks"></a>备注  
 CorDebugRegister 枚举的值指定不同微处理器的寄存器。 每个值的上限五位均为的索引为`availableRegChunks`的字节数组。 每个值的较低的三个位标识中的索引的字节的位位置。 给定`CorDebugRegister`值，该值指定特定的注册，掩码中的寄存器的位置确定，如下所示：  
  
1.  提取所需访问中的正确字节的索引`availableRegChunks`数组：  
  
     `CorDebugRegister`值 >> 3  
  
2.  提取其中位零是最低有效位的位位置中的索引的字节：  
  
     `CorDebugRegister`值 （&) 7  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [ICorDebugRegisterSet 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
