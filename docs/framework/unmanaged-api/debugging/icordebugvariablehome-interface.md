---
title: ICorDebugVariableHome 接口
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: 306a07450b8ae6d29875ca0cc4679390472e4d1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121044"
---
# <a name="icordebugvariablehome-interface"></a>ICorDebugVariableHome 接口
表示函数的局部变量或自变量。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetArgumentIndex 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|获取函数参数的索引。|  
|[GetCode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|获取包含此 `ICorDebugVariableHome` 对象的 "ICorDebugCode" 实例。|  
|[GetLiveRange 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|获取此变量的生存期的本机范围。|  
|[GetLocationType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|获取变量的本机位置的类型。|  
|[GetOffset 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|获取与基寄存器相对应的偏移量。|  
|[GetRegister 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|获取一个寄存器，其中包含位置类型为 `VLT_REGISTER`的变量，以及位置类型为 `VLT_REGISTER_RELATIVE`的变量的基寄存器。|  
|[GetSlotIndex 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|获取本地变量的托管槽索引。|  
  
## <a name="example"></a>示例  
 下面的代码片段使用名为 `pCode4`的[ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)对象。  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugVariableHomeEnum 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
