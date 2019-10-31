---
title: ICorDebugILFrame4::GetLocalVariableEx 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: fb2744493d89a57ffc78e194f8c1e4a6dcf9f7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090921"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a>ICorDebugILFrame4::GetLocalVariableEx 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 获取此中间语言 (IL) 堆栈帧中指定的局部变量的值，并且（可选）访问在探查器 ReJIT 检测中添加的变量。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `flags`  
 中一个[ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)枚举成员，用于指定在探查器 ReJIT 检测中添加的变量是否包含在帧中。  
  
 `dwIndex`  
 [in] IL 堆栈帧中局部变量的索引。  
  
 `ppValue`  
 弄指向表示检索到的值的 "ICorDebugValue" 对象地址的指针。  
  
## <a name="remarks"></a>备注  
 此方法类似于[GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)方法，不同之处在于它还可以访问在探查器 ReJIT 检测中添加的变量。 使用 `ILCODE_ORIGINAL_IL` 的 `flags` 值调用此方法等效于调用[GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md);如果用附加的局部变量检测方法，则不能访问这些变量。 `ILCODE_REJIT_IL` 使调试器能够访问在探查器 ReJIT 检测中添加的局部变量。 如果未检测到 IL，则此方法将返回 `E_INVALIDARG`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugILFrame4 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT：操作方法指南](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
