---
title: "ICLRRuntimeHost::ExecuteApplication 方法"
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
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b765f020bd15fa94fb18a6fd7d81cf66c534639
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication 方法
在基于清单的 ClickOnce 部署方案中用于指定要在新域中激活的应用程序。 有关这些方案的详细信息，请参阅[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzAppFullName`  
 [in]应用程序，如为定义的完整名称<xref:System.ApplicationIdentity>。  
  
 `dwManifestPaths`  
 [in]字符串中包含的数量`ppwzManifestPaths`数组。  
  
 `ppwzManifestPaths`  
 [in] 可选。 包含应用程序的清单路径的字符串数组。  
  
 `dwActivationData`  
 [in]字符串中包含的数量`ppwzActivationData`数组。  
  
 `ppwzActivationData`  
 [in] 可选。 包含应用程序的激活数据，例如部署在 Web 应用程序的 URL 的查询字符串部分的字符串数组。  
  
 `pReturnValue`  
 [out]从应用程序的入口点返回的值。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `ExecuteApplication`用于激活新创建的应用程序域中的 ClickOnce 应用程序。  
  
 `pReturnValue`输出参数设置为应用程序返回的值。 如果提供的值为 null 的`pReturnValue`，`ExecuteApplication`不会失败，但它不返回值。  
  
> [!IMPORTANT]
>  不要调用[启动方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法之前调用`ExecuteApplication`激活基于清单的应用程序的方法。 如果`Start`首先，调用方法`ExecuteApplication`方法调用将失败。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [ICLRRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [SetAppDomainManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [演练：在设计器中使用 ClickOnce 部署 API 按需下载程序集](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
