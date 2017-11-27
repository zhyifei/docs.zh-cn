---
title: "ICorDebugRegisterSet::GetRegisters 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7edae3d3be1bcfb80b7a1e432fd5f25e119f078f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters 方法
（在计算机上当前正在执行代码） 中获取的每个寄存器的值指定的位掩码。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `mask`  
 [in]指定哪一寄存器的值为要检索一个位掩码。 每位对应于寄存器。 如果位设置为 1，则检索寄存器的值;否则，不会检索寄存器的值。  
  
 `regCount`  
 [in]要检索的寄存器值的数目。  
  
 `regBuffer`  
 [out]数组`CORDB_REGISTER`对象，其中每个接收的寄存器的值。  
  
## <a name="remarks"></a>备注  
 数组的大小应等于的中位掩码设置为 1 的位数。 `regCount`参数指定将接收寄存器值的缓冲区中的元素数。 如果`regCount`值是由屏蔽指示的寄存器的数目太小，将从集合中截断的更高版本的编号的寄存器。 如果`regCount`值太大，未使用`regBuffer`元素将保持不变。  
  
 如果位掩码指定不可用，注册`GetRegisters`返回该寄存器的不确定的值。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugRegisterSet 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
