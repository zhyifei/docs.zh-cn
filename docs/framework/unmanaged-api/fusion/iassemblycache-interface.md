---
title: "IAssemblyCache 接口"
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
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21ebc29a6c442625f7a532f7b1e6a47e7dc4cb69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycache-interface"></a>IAssemblyCache 接口
合成技术表示使用全局程序集缓存。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateAssemblyCacheItem 方法](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|获取一个新的引用[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)。|  
|[CreateAssemblyScavenger 方法](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|保留供内部使用合成技术。|  
|[InstallAssembly 方法](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|将指定的程序集安装在全局程序集缓存中。|  
|[QueryAssemblyInfo 方法](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|获取有关指定的程序集的请求的数据。|  
|[UninstallAssembly 方法](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|从全局程序集缓存中卸载指定的程序集。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [全局程序集缓存](../../../../docs/framework/app-domains/gac.md)
