---
title: ICorDebugCode3::GetReturnValueLiveOffset 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: 34d543dd76de05bdf55d8187cf192455d1387a9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178943"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>ICorDebugCode3::GetReturnValueLiveOffset 方法
对于指定的 IL 偏移量，获取应放置断点的本机偏移，以便调试器可以从函数获取返回值。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,
    [out] ULONG32 *pFetched,
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a>parameters  
 `ILoffset`  
 IL 偏移量。 它必须是函数调用站点，否则函数调用将失败。  
  
 `bufferSize`  
 可用于存储`pOffsets`的字节数。  
  
 `pFetched`  
 指向实际返回的偏移量数的指针。 通常，其值为 1，但单个 IL 指令可以映射到`CALL`多个程序集指令。  
  
 `pOffsets`  
 本机偏移的数组。 通常，`pOffsets`包含单个偏移量，尽管单个 IL 指令可以映射到多个映射到多个`CALL`程序集指令。  
  
## <a name="remarks"></a>备注  
 此方法与[ICorDebugILFrame3：：getReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)方法一起使用，以获取返回引用类型的方法的返回值。 将 IL 偏移传递到函数调用站点到此方法返回一个或多个本机偏移。 然后，调试器可以在函数中的这些本机偏移设置断点。 当调试器到达其中一个断点时，您可以将传递给此方法的相同 IL 偏移传递给[ICorDebugILFrame3：：：：getReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)方法以获得返回值。 然后，调试器应清除它设置的所有断点。  
  
> [!WARNING]
> 和`ICorDebugCode3::GetReturnValueLiveOffset` [ICorDebugILFrame3：：获取回归价值ForIL偏移](icordebugilframe3-getreturnvalueforiloffset-method.md)方法允许您仅获取参考类型的返回值信息。 不支持从值类型（即派生自<xref:System.ValueType>的所有类型）检索返回值信息。  
  
 函数返回下表中显示的`HRESULT`值。  
  
|`HRESULT` 值|说明|  
|---------------------|-----------------|  
|`S_OK`|成功。|  
|`CORDBG_E_INVALID_OPCODE`|给定的 IL 偏移站点不是呼叫指令，或函数返回`void`。|  
|`CORDBG_E_UNSUPPORTED`|给定的 IL 偏移量是适当的调用，但返回类型对于获取返回值不受支持。|  
  
 该方法`ICorDebugCode3::GetReturnValueLiveOffset`仅适用于基于 x86 和 AMD64 的系统。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [GetReturnValueForILOffset 方法](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [ICorDebugCode3 接口](icordebugcode3-interface.md)
