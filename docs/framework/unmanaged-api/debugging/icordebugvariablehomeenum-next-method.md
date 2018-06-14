---
title: ICorDebugVariableHomeEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5ab18d6c2ae8bbf47a3bcd7cb892530be4f8f4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421579"
---
# <a name="icordebugvariablehomeenumnext-method"></a>ICorDebugVariableHomeEnum::Next 方法
获取指定的数目的[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)包含有关本地变量和函数中的自变量的信息的实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in] 要检索的对象数。  
  
 `homes`  
 一个指针，其中每个指向数组[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)提供有关本地变量或函数参数的信息的对象。  
  
 `pceltFetched`  
 [out]在对象中实际返回的实例数。  
  
## <a name="return-value"></a>返回值  
 该方法返回以下值。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|该方法已成功完成。|  
|`S_FALSE`|检索实例的实际数量，具体体现在`pceltFetched`，小于请求的实例数。|  
  
## <a name="remarks"></a>备注  
 [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)方法检索的最多`celt`对象的枚举器当前位置开始。 方法返回时，`pceltFetched`包含的实际检索的对象数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugVariableHomeEnum 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 [ICorDebugVariableHome 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
