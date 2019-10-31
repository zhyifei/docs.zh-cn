---
title: ICorDebugRegisterSet2::GetRegistersAvailable 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: d0b6960a24e246c7a538e8ffc59fa380a4b8e2a7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131372"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable 方法
获取提供可用寄存器的位图的字节数组。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `numChunks`  
 [in] `availableRegChunks` 数组的大小。  
  
 `availableRegChunks`  
 弄字节数组，其中每个位对应于寄存器。 如果寄存器可用，则会设置寄存器的相应位。  
  
## <a name="remarks"></a>备注  
 CorDebugRegister 枚举的值指定不同微处理器的寄存器。 每个值的上限为 `availableRegChunks` 字节数组中的索引。 每个值的下三位标识索引字节内的位位置。 给定一个指定特定寄存器的 `CorDebugRegister` 值时，将按如下所示确定此寄存器在掩码中的位置：  
  
1. 提取访问 `availableRegChunks` 数组中正确字节所需的索引：  
  
     `CorDebugRegister` 值 > > 3  
  
2. 提取索引字节内的位位置，其中位零是最小有效位：  
  
     `CorDebugRegister` 值 & 7  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
