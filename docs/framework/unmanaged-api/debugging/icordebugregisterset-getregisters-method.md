---
title: ICorDebugRegisterSet::GetRegisters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 112d530c765fc74ab4ea767cb3168977d1b45f47
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138367"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters 方法
获取位掩码指定的每个寄存器的值（在当前正在执行代码的计算机上）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `mask`  
 中指定要检索的寄存器值的位掩码。 每个位对应于一个寄存器。 如果将位设置为1，则将检索寄存器的值;否则，不检索寄存器的值。  
  
 `regCount`  
 中要检索的寄存器值的数目。  
  
 `regBuffer`  
 弄`CORDB_REGISTER` 对象的数组，其中每个对象都接收寄存器的值。  
  
## <a name="remarks"></a>备注  
 数组的大小应等于位掩码中设置为1的位数。 `regCount` 参数指定将接收寄存器值的缓冲区中的元素数。 如果 `regCount` 值对于掩码指示的寄存器数量太小，则将从该集中截断编号较高的寄存器。 如果 `regCount` 值太大，则不会修改未使用的 `regBuffer` 元素。  
  
 如果位掩码指定的寄存器不可用，`GetRegisters` 将为该寄存器返回一个不确定的值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugRegisterSet 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
