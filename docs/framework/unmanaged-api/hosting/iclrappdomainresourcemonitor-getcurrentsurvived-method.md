---
title: "ICLRAppDomainResourceMonitor::GetCurrentSurvived 方法"
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
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 612e27120196d2920b75c030929af1807d4a336f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived 方法
获取最后一个完整、 阻碍性垃圾回收后保留下来的、 由当前的应用程序域引用的字节数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a>参数  
 `dwAppDomainId`  
 [in]请求的应用程序域的 ID。  
  
 `pAppDomainBytesSurvived`  
 [out]指向最后一个垃圾回收后仍存在此应用程序域所持有的字节数的指针。 完整回收之后，此数字应准确且完整。 暂时回收之后，此编号是可能不完整。 此参数可以为 `null`。  
  
 `pRuntimeBytesSurvived`  
 [out]指向的从上一次垃圾回收后保留下来的字节总数的指针。 完整回收之后，此数字表示托管堆中保留的字节数。 暂时回收之后，此数字表示暂时生成中实时保留的字节数。 此参数可以为 `null`。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|COR_E_APPDOMAINUNLOADED|应用程序域已被卸载，或不存在。|  
  
## <a name="remarks"></a>备注  
 只有在完整、 阻碍性垃圾回收; 之后更新统计信息也就是说，的集合包含所有代并停止应用程序时集合时发生。 例如，<xref:System.GC.Collect?displayProperty=nameWithType>方法重载执行的完整、 阻碍性回收。 并发垃圾回收发生在后台，并且不会阻止应用程序。  
  
 `GetCurrentSurvived`方法是托管的非托管等效项<xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>属性。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAppDomainResourceMonitor 接口](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [应用程序域资源监视](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
