---
title: "ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2781cfb1e23db02ab8192c78bd0a3e585ee28b2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法
获取自应用程序域创建以来在当前的应用程序域中，执行时使用的所有线程的总处理器时间。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a>参数  
 `dwAppDomainId`  
 [in]请求的应用程序域的 ID。  
  
 `pMilliseconds`  
 [out]指向自应用程序域创建以来在当前的应用程序域中执行时使用的所有线程的总处理器时间的指针。 此参数可以为 `null`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|COR_E_APPDOMAINUNLOADED|应用程序域已被卸载，或不存在。|  
|E_FAIL|未启用应用程序域资源监视。<br /><br /> 或<br /><br /> 所有其他故障。|  
  
## <a name="remarks"></a>备注  
 此方法是托管的非托管等效项<xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>属性。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAppDomainResourceMonitor 接口](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [应用程序域资源监视](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
