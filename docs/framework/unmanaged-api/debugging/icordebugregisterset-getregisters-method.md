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
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178542"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters 方法
获取位掩码指定的每个寄存器的值（当前正在执行代码的计算机）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>parameters  
 `mask`  
 [在]指定要检索哪些寄存器值的位掩码。 每个位对应于寄存器。 如果位设置为 1，则检索寄存器的值;如果位设置为 1，则检索寄存器的值。否则，不会检索寄存器的值。  
  
 `regCount`  
 [在]要检索的寄存器值数。  
  
 `regBuffer`  
 [出]对象数组`CORDB_REGISTER`，每个对象都接收寄存器的值。  
  
## <a name="remarks"></a>备注  
 数组的大小应等于位掩码中设置为 1 的位数。 参数`regCount`指定将接收寄存器值的缓冲区中的元素数。 如果`regCount`该值对于掩码指示的寄存器数太小，则较高的编号寄存器将从集中截断。 如果`regCount`该值太大，则未使用`regBuffer`的元素将取消修改。  
  
 如果位掩码指定不可用的寄存器，`GetRegisters`则返回该寄存器的不确定值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugRegisterSet 接口](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 接口](icordebugregisterset2-interface.md)
