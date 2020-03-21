---
title: ICorDebugILFrame3::GetReturnValueForILOffset 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 0d1ef6c1369fd399f5b36b24a21c4b5d7f1e80fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178817"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset 方法
获取封装函数返回值的"ICorDebugValue"对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>parameters  
 `ILOffset`  
 IL 偏移量。 请参阅“备注”部分。  
  
 `ppReturnValue`  
 指向"ICorDebugValue"接口对象的地址的指针，该对象提供有关函数调用的返回值的信息。  
  
## <a name="remarks"></a>备注  
 此方法与[ICorDebugCode3：：getReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md)方法一起使用，以获得方法的返回值。 对于返回值被忽略的方法，它特别有用，如下两个代码示例所示。 第一个示例调用<xref:System.Int32.TryParse%2A?displayProperty=nameWithType>方法，但忽略该方法的返回值。  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 第二个示例说明了调试中更常见的问题。 由于方法在方法调用中用作参数，因此仅当调试器通过调用的方法时，才能访问其返回值。 在许多情况下，尤其是在外部库中定义被调用的方法时，这是不可能的。  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 如果将[ICorDebugCode3：：获取返回ValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md)方法 IL 偏移传递给函数调用站点，它将返回一个或多个本机偏移。 然后，调试器可以在函数中的这些本机偏移设置断点。 当调试器到达其中一个断点时，可以传递传递给此方法的相同 IL 偏移量以获得返回值。 然后，调试器应清除它设置的所有断点。  
  
> [!WARNING]
> [ICorDebugCode3：：获取回归价值实时偏移法](icordebugcode3-getreturnvalueliveoffset-method.md)和方法`ICorDebugILFrame3::GetReturnValueForILOffset`允许您仅获取参考类型的返回值信息。 不支持从值类型（即派生自<xref:System.ValueType>的所有类型）检索返回值信息。  
  
 `ILOffset`参数指定的 IL 偏移量应位于函数调用站点，调试器应在[ICorDebugCode3：getReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md)方法为同一 IL 偏移量返回的本机偏移器处的断点设置处停止。 如果调试器未停止在指定 IL 偏移的正确位置，则 API 将失败。  
  
 如果函数调用不返回值，API 将失败。  
  
 该方法`ICorDebugILFrame3::GetReturnValueForILOffset`仅适用于基于 x86 和 AMD64 的系统。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [GetReturnValueLiveOffset 方法](icordebugcode3-getreturnvalueliveoffset-method.md)
- [ICorDebugILFrame3 接口](icordebugilframe3-interface.md)
