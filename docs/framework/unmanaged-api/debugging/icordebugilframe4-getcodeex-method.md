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
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178782"
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
  
## <a name="parameters"></a>parameters  
 `flags`  
 [在][ILCodeKind](ilcodekind-enumeration.md)枚举成员，用于指定探查器的 ReJIT 请求定义的中间语言 （IL） 是否包含在框架中。  
  
 `ppCode`  
 [出]指向"ICorDebugCode"对象地址的指针，该对象表示此堆栈帧正在执行的代码。  
  
## <a name="remarks"></a>备注  
 此方法类似于[ICorDebugFrame：getCode](icordebugframe-getcode-method.md)方法，只不过它可以选择访问探查器的 ReJIT 请求定义的代码。 使用`flags`的值`ILCODE_ORIGINAL_IL`调用此方法等效于调用[GetCode](icordebugframe-getcode-method.md)。如果检测该方法，则无法访问其 IL。 `ILCODE_REJIT_IL` 允许调试器访问由探查器的 ReJIT 请求定义的 IL。 如果未检测 IL ，`ppCode`则为**null，** 并且该方法返回`S_OK`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugILFrame4 接口](icordebugilframe4-interface.md)
- [调试接口](debugging-interfaces.md)
- [ReJIT：指南](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
