---
title: "ICorDebugILCode2::GetLocalVarSigToken 方法"
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
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47004375194438b1ef0aaf61144ba6f16278545b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a>ICorDebugILCode2::GetLocalVarSigToken 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 获取元数据标记，用于由此实例表示的函数的局部变量签名。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pmdSig`  
 [out] 指向此函数的局部变量签名的 `mdSignature` 标记，或者指向 `mdSignatureNil`（如果不存在签名，即该函数没有任何局部变量）的指针。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugILCode2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
