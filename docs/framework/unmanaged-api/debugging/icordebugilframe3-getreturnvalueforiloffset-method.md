---
title: "ICorDebugILFrame3::GetReturnValueForILOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c58319de99bdd8d7cce0ea55ccb3140a31a39bd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset 方法
获取封装函数的返回值的"ICorDebugValue"对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ILOffset`  
 IL 偏移量。 请参见“备注”部分。  
  
 `ppReturnValue`  
 提供有关返回值的函数调用信息"ICorDebugValue"接口对象的地址指向的指针。  
  
## <a name="remarks"></a>备注  
 此方法使用连同[icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法以获取方法的返回值。 它将在其返回值将被忽略，如下面的两个代码示例所示的方法的情况下特别有用。 第一个示例调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法，但将忽略方法的返回值。  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 第二个示例阐释得更加常见调试问题。 由于方法用作方法调用中的参数，因此，仅当，调试器逐句通过调用的方法，才可访问其返回值。 在许多情况下，尤其是当调用的方法定义在外部的库中，这是不可行。  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 如果你通过[icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)的 IL 偏移量到函数的调用站点的方法，它将返回一个或多个本机偏移量。 调试器然后可以在这些函数中的本机偏移量上设置断点。 当调试器遇到的其中一个断点时，然后可以将相同的 IL 偏移量传递给此方法以获取返回值进行传递。 调试器然后应清除它所设置的所有断点。  
  
> [!WARNING]
>  [Icordebugcode3:: Getreturnvalueliveoffset 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)和`ICorDebugILFrame3::GetReturnValueForILOffset`方法，你可以获取仅适用于引用类型的返回值信息。 从值类型检索返回值信息 (即，派生自的所有类型<xref:System.ValueType>) 不支持。  
  
 指定的 IL 偏移量`ILOffset`参数应在函数调用站点上，并应在返回的本机偏移量处设置断点处停止调试对象[icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)方法为相同的 IL 偏移量。 如果在指定的 IL 偏移量的正确位置不停止调试对象，该 API 将失败。  
  
 如果函数调用不返回值，该 API 将失败。  
  
 `ICorDebugILFrame3::GetReturnValueForILOffset`方法是仅适用于基于 x86 和 AMD64 系统。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetReturnValueLiveOffset 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [ICorDebugILFrame3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
