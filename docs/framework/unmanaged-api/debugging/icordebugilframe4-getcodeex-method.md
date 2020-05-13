---
title: ICorDebugILFrame4::GetCodeEx 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: 582e28c18f36b253425b1e0a2034cdd262fddd57
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213733"
---
# <a name="icordebugilframe4getcodeex-method"></a>ICorDebugILFrame4::GetCodeEx 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 获取指向此堆栈帧正在执行的代码的指针。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>参数  
 `flags`  
 中一个[ILCodeKind](ilcodekind-enumeration.md)枚举成员，该成员指定由探查器的 ReJIT 请求定义的中间语言（IL）是否包含在帧中。  
  
 `ppCode`  
 弄一个指向 "ICorDebugCode" 对象地址的指针，该对象表示此堆栈帧正在执行的代码。  
  
## <a name="remarks"></a>备注  
 此方法类似于[ICorDebugFrame：： GetCode](icordebugframe-getcode-method.md)方法，不同之处在于它可以访问由探查器的 ReJIT 请求定义的代码。 使用的值调用此方法 `flags` `ILCODE_ORIGINAL_IL` 等效于调用[GetCode](icordebugframe-getcode-method.md); 如果检测到此方法，则将无法访问其 IL。 `ILCODE_REJIT_IL` 允许调试器访问由探查器的 ReJIT 请求定义的 IL。 如果未检测到 IL， `ppCode` 则为**null**，并且该方法将返回 `S_OK` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugILFrame4 接口](icordebugilframe4-interface.md)
- [调试接口](debugging-interfaces.md)
- [ReJIT：操作方法指南](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
