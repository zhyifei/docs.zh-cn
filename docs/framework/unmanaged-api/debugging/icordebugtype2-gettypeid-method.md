---
title: "ICorDebugType2::GetTypeID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugType2.GetTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d18aa8210ea90736c0757e2587aab4ff143dcdad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2::GetTypeID 方法
获取[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)此类型。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 [out]指向的指针[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)为此 ICorDebugType。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。 `HRESULT`代码如下：  
  
|返回代码|描述|  
|-----------------|-----------------|  
|`S_OK`|方法成功。 该方法已检索有效[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)。|  
|`CORDBG_E_CLASS_NOT_LOADED`|尚未加载该类型。|  
|`CORDBG_E_UNSUPPORTED`|不支持的类型。|  
  
## <a name="remarks"></a>备注  
 此方法从 ICorDebugType，表示可能或可能不具有已加载到运行时，为的类型提供映射[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)，后者相当于一个不透明处理标识入运行时加载的类型。  
  
 当 ICorDebugType 表示的类型，但尚未被加载，则此方法返回`CORDBG_E_CLASS_NOT_LOADED`。  如果不支持的类型，它将返回`CORDBG_E_UNSUPPORTED`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugType2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
