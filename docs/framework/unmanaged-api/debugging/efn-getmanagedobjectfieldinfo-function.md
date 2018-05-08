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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6195d9666afa8fba3f77322366e4709634e53bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="efngetmanagedobjectfieldinfo-function"></a>_EFN_GetManagedObjectFieldInfo 函数
使用提供的对象指针和字段名，获取从对象的开头到字段和字段值的偏移量。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a>参数  
 `Client`  
 [in]指向调试客户端的指针。  
  
 `objAddr`  
 [in]托管的对象指针。  
  
 szFieldName  
 [in]指向字段名称的托管的对象指针。  
  
 `pValue`  
 [out]字段值。 此参数可以为 null。  
  
 `pOffset`  
 [out]从的偏移量`objAddr`到字段。 此参数可以为 null。  
  
## <a name="remarks"></a>备注  
 如果偏移量为 0，则写入没有偏移量。  
  
 如果没有任何托管的代码的线程上当前上下文中，该函数将返回的错误代码为 0x1000 0xa0 设施值与 HRESULT SOS_E_NOMANAGEDCODE。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** SOS_Stacktrace.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试全局静态函数](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
