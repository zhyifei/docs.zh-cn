---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: b411190ff36410c1d293f1e48b31975be8a13aee
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616029"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法
获取自应用程序域创建以来在当前应用程序域中执行时所有线程已使用的总处理器时间。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>参数  
 `dwAppDomainId`  
 中请求的应用程序域的 ID。  
  
 `pMilliseconds`  
 弄一个指针，指向自创建应用程序域后，所有线程在当前应用程序域中执行时所使用的总处理器时间。 此参数可以为 `null`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|COR_E_APPDOMAINUNLOADED|应用程序域已卸载或不存在。|  
|E_FAIL|未启用应用程序域资源监视。<br /><br /> -或-<br /><br /> 所有其他失败。|  
  
## <a name="remarks"></a>备注  
 此方法是托管属性的非托管等效项 <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRAppDomainResourceMonitor 接口](iclrappdomainresourcemonitor-interface.md)
- [承载接口](hosting-interfaces.md)
- [应用程序域资源监视](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [承载](index.md)
