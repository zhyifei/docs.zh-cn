---
title: "ICorDebugRegisterSet2::GetRegisters 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.GetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f9deccff09c255b339a22af711906baf23d7df9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2::GetRegisters 方法
获取的值的每个寄存器 （当前执行代码的平台） 指定给定的位掩码。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `maskCount`  
 [in]大小，以字节为单位的`mask`数组。  
  
 `mask`  
 [in]字节数组，其中每位对应于寄存器。 如果位是 1，则将检索相应的寄存器的值。  
  
 `regCount`  
 [in]要检索的寄存器值的数目。  
  
 `regBuffer`  
 [out]数组`CORDB_REGISTER`对象，其中每个接收的寄存器的值。  
  
## <a name="remarks"></a>备注  
 `GetRegisters`方法返回从指定的掩码的寄存器的值的数组。 数组不包含未设置其掩码位寄存器值。 因此，大小`regBuffer`数组必须等于掩码中的 1 的数。 如果值`regCount`是太小，将从集合中截断的掩码，较高的编号寄存器的值指示的寄存器的数量。 如果`regCount`太大，未使用`regBuffer`元素将保持不变。  
  
 如果掩码指示寄存器不可用，则将为该寄存器返回不确定的值。  
  
 `ICorDebugRegisterSet2::GetRegisters`方法是为具有 64 个以上寄存器的平台必需的。 例如，IA64 有 128 个通用寄存器和 128 浮点寄存器，因此您需要超过 64 位的位掩码。  
  
 如果因为是在如 x86、 的平台上的这种情况不具有 64 个以上寄存器`GetRegisters`方法实际上就是将转换中的字节`mask`到字节数组`ULONG64`，然后调用[ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)方法，后者采用`ULONG64`掩码。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [ICorDebugRegisterSet 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
