---
title: ICLRRuntimeHost::UnloadAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: 293c1764f4c0d857138726b8ed4855b1e3b03116
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703920"
---
# <a name="iclrruntimehostunloadappdomain-method"></a>ICLRRuntimeHost::UnloadAppDomain 方法
卸载 <xref:System.AppDomain> 与指定数值标识符对应的托管。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwAppDomainId`  
 中要卸载的应用程序域的数值标识符。  
  
 `fWaitUntilDone`  
 [in] `true`指示公共语言运行时（CLR）在尝试卸载应用程序域之前必须等待，直到它完成执行应用程序的当前线程。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`UnloadAppDomain`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 可以通过调用[GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md)获取当前线程正在其中执行的应用程序域的数值标识符。 此标识符与 <xref:System.AppDomain.Id%2A> 托管类型的属性相对应 <xref:System.AppDomain> 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRRuntimeHost 接口](iclrruntimehost-interface.md)
