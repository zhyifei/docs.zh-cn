---
title: "ICorDebugCode3::GetReturnValueLiveOffset 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d10d298a031e7146eaf6cf7988538e6f7020136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>ICorDebugCode3::GetReturnValueLiveOffset 方法
对于指定的 IL 偏移量，获取本机偏移量，以便调试器可以获取返回值从函数应放置断点。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ILoffset`  
 IL 偏移量。 它必须是函数调用站点，否则函数调用将失败。  
  
 `bufferSize`  
 可用于存储的字节数`pOffsets`。  
  
 `pFetched`  
 指向的实际返回的偏移量数的指针。 通常情况下，其值为 1，但单个 IL 指令可以映射到多个`CALL`程序集指令。  
  
 `pOffsets`  
 本机偏移量的数组。 通常情况下，`pOffsets`尽管单个 IL 指令可以映射到多个映射到多个包含同一偏移量，`CALL`程序集指令。  
  
## <a name="remarks"></a>备注  
 此方法使用连同[icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法以获取返回引用类型的方法的返回值。 传递 IL 偏移量到函数调用站点到此方法返回一个或多个本机偏移量。 调试器然后可以在这些函数中的本机偏移量上设置断点。 当调试器遇到的其中一个断点时，你就可以将相同的 IL 偏移量传递给此方法传递[icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法以获取返回值。 调试器然后应清除它所设置的所有断点。  
  
> [!WARNING]
>  `ICorDebugCode3::GetReturnValueLiveOffset`和[icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)方法，你可以获取仅适用于引用类型的返回值信息。 从值类型检索返回值信息 (即，派生自的所有类型<xref:System.ValueType>) 不支持。  
  
 该函数将返回`HRESULT`下表中所示的值。  
  
|`HRESULT` 值|描述|  
|---------------------|-----------------|  
|`S_OK`|成功。|  
|`CORDBG_E_INVALID_OPCODE`|给定的 IL 偏移量的站点不是调用指令，或该函数将返回`void`。|  
|`CORDBG_E_UNSUPPORTED`|给定的 IL 偏移量是正确的调用，但返回类型不支持获取返回值。|  
  
 `ICorDebugCode3::GetReturnValueLiveOffset`方法是仅适用于基于 x86 和 AMD64 系统。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetReturnValueForILOffset 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [ICorDebugCode3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
