---
title: "ECustomDumpFlavor 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a063dd6b50566d0bff393853015efc6a15f8cee1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor 枚举
包含值，用于指示哪些项目应包含自定义子集中的堆转储时报告错误。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|指定自定义的堆转储应该以小型转储启动并包含指定的任何额外数据[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)实例传递给相同的方法。|  
|`DUMP_FLAVOR_NonHeapCLRState`|指定自定义的堆转储应收集未动态分配的所有运行时状态数据。|  
  
## <a name="remarks"></a>备注  
 类型的参数`ECustomDumpFlavor`传递给[iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ECustomDumpItemKind 枚举](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [ICLRErrorReportingManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
