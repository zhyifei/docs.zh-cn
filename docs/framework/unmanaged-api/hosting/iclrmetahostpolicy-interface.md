---
title: "ICLRMetaHostPolicy 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy
helpviewer_keywords: ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b8cbe1d397e1214cfa4d3f4cbc3d6cdf2d3ccd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy 接口
提供[GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法，将指针返回到基于策略条件的公共语言运行时 (CLR) 接口，托管程序集、 版本和配置文件。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetRequestedRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|提供了首选的 CLR 接口基于策略条件、 托管程序集、 版本和配置文件。|  
  
## <a name="remarks"></a>备注  
 你可以通过调用获取对此接口的引用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数如下面的代码所示：  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  此接口不实际上不会加载或激活 CLR，但只需返回的首选的 CLR 版本基于安装或未加载的可用版本。  
  
 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]托管 API 将合并策略，以便的特定需求的主机可以使用基本功能，而不会产生意外的损失。 例如，许多 MSCorEE.dll 导出将绑定到特定的 CLR，虽然方法可能逻辑上需要它。 [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)枚举提供了所共有的大部分主机的绑定策略。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [CLR 承载接口添加在.NET Framework 4 和 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
