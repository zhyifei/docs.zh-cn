---
title: IGCHost::SetGCStartupLimits 方法
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87ba947b9564f82f8daf8cd2ba0acac5cc3587ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928665"
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits 方法
设置第0代的段大小和最大大小。  
  
> [!IMPORTANT]
> 从 .NET Framework 4.5 开始, 可以使用[IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法将段大小和最大第 0 `DWORD`代大小设置为大于的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>参数  
 `SegmentSize`  
 中垃圾收集系统使用的段大小。  
  
 `MaxGen0Size`  
 中第0代的最大大小。  
  
## <a name="remarks"></a>备注  
 `SetGCStartupLimits`方法只能调用一次。 以后不能更改这些值。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost, GCHost  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IGCHost 接口](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
