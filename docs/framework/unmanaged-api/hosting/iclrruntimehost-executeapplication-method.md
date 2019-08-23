---
title: ICLRRuntimeHost::ExecuteApplication 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965358"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication 方法
在基于清单的 ClickOnce 部署方案中用于指定要在新域中激活的应用程序。 有关这些方案的详细信息, 请参阅[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `pwzAppFullName`  
 中为定义<xref:System.ApplicationIdentity>的应用程序的完整名称。  
  
 `dwManifestPaths`  
 中`ppwzManifestPaths`数组中包含的字符串的数目。  
  
 `ppwzManifestPaths`  
 [in] 可选。 包含应用程序的清单路径的字符串数组。  
  
 `dwActivationData`  
 中`ppwzActivationData`数组中包含的字符串的数目。  
  
 `ppwzActivationData`  
 [in] 可选。 一个字符串数组, 其中包含应用程序的激活数据, 如通过 Web 部署的应用程序的 URL 的查询字符串部分。  
  
 `pReturnValue`  
 弄从应用程序的入口点返回的值。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时, 该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 如果某个方法返回 E_FAIL, 则 CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `ExecuteApplication`用于在新创建的应用程序域中激活 ClickOnce 应用程序。  
  
 `pReturnValue` Output 参数设置为应用程序返回的值。 如果为`pReturnValue`提供 null 值, `ExecuteApplication`则不会失败, 但它不返回值。  
  
> [!IMPORTANT]
> 请不要在调用`ExecuteApplication`方法之前调用[Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法来激活基于清单的应用程序。 如果首先调用`ExecuteApplication`方法,方法调用将失败。 `Start`  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [ICLRRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [SetAppDomainManager 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [演练：在设计器中使用 ClickOnce 部署 API 按需下载程序集](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
