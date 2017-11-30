---
title: "ModuleBindInfo 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ModuleBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ModuleBindInfo
helpviewer_keywords: ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6488503e0300530b22c0c6f904e11db7f5d5b41c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo 结构
提供有关引用的模块和包含它的程序集的详细的信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`dwAppDomainId`|唯一标识符`IStream`返回通过调用[ihostassemblystore:: Providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)方法，为要加载引用的模块。|  
|`lpAssemblyIdentity`|包含引用的模块程序集的唯一标识符。|  
|`lpModuleName`|引用的模块的名称。|  
  
## <a name="remarks"></a>备注  
 `ModuleBindInfo`作为参数传递给传递`IHostAssemblyStore::ProvideModule`。 主机提供的唯一标识符`dwAppDomainId`公共语言运行时 (CLR)。 调用了[ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)方法返回时，运行时使用标识符来确定是否的内容`IStream`已映射。 如果是这样，则运行时将加载现有的副本，而不是无需重新映射流。 运行时将此标识符还用作查找键从调用返回的流的`IHostAssemblyStore::ProvideAssembly`方法。 因此，该标识符必须是唯一的模块的请求与程序集请求。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.idl  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [AssemblyBindInfo 结构](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [ICLRAssemblyIdentityManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
