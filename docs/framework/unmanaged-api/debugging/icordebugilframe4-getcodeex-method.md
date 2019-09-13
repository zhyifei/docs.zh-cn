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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb50459e36cfeb76a0c9a1e1cd4544260d484f45
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926801"
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
 中一个[ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)枚举成员，该成员指定由探查器的 ReJIT 请求定义的中间语言（IL）是否包含在帧中。  
  
 `ppCode`  
 弄一个指向 "ICorDebugCode" 对象地址的指针，该对象表示此堆栈帧正在执行的代码。  
  
## <a name="remarks"></a>备注  
 此方法类似于[ICorDebugFrame：： GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)方法，不同之处在于它可以访问由探查器的 ReJIT 请求定义的代码。 使用`flags`的`ILCODE_ORIGINAL_IL`值调用此方法等效于调用[GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); 如果检测到此方法，则将无法访问其 IL。 `ILCODE_REJIT_IL` 允许调试器访问由探查器的 ReJIT 请求定义的 IL。 如果未检测到 IL， `ppCode`则为**null**，并且该方法将`S_OK`返回。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugILFrame4 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT操作方法指南](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
