---
title: _EFN_GetManagedObjectFieldInfo 函数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: b68f24908a5b214d507da8e8a4636a7c55259604
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123016"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a>\_EFN\_GetManagedObjectFieldInfo 函数
使用提供的对象指针和字段名，获取从对象的开头到字段和字段值的偏移量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a>参数  
 `Client`  
 中指向调试客户端的指针。  
  
 `objAddr`  
 中托管对象指针。  
  
 szFieldName  
 中指向字段名称的托管对象指针。  
  
 `pValue`  
 弄字段值。 此参数可以为 null。  
  
 `pOffset`  
 弄从 `objAddr` 到字段的偏移量。 此参数可以为 null。  
  
## <a name="remarks"></a>备注  
 如果偏移量为0，则不写入偏移量。  
  
 如果当前在上下文中的线程上没有托管代码，则该函数将返回 HRESULT SOS_E_NOMANAGEDCODE，其设施值为0xa0，错误代码为0x1000。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** SOS_Stacktrace  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试全局静态函数](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
