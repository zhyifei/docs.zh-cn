---
title: "ICorRuntimeHost::NextDomain 方法"
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
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e539cd4071fe9713ed53f66c2f67b24b787d259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostnextdomain-method"></a>ICorRuntimeHost::NextDomain 方法
枚举中的下一个域中获取的接口指针。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>参数  
 `hEnum`  
 [in]枚举器已通过调用[EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)。  
  
 `pAppDomain`  
 [out]接口指针<xref:System._AppDomain?displayProperty=nameWithType>表示下一个域中的枚举或为 null，如果没有更多域存在的类型。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该操作成功。|  
|S_FALSE|操作无法完成，或在枚举中的没有更多域。|  
|E_FAIL|发生了未知的灾难性故障。 如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。 对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** 1.0、 1.1  
  
## <a name="see-also"></a>请参阅  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
