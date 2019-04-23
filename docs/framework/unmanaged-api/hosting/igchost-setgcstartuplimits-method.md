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
ms.openlocfilehash: 365261883f0b81884bb7cf70614628c05f9067c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221002"
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits 方法
设置第 0 代段大小和最大大小。  
  
> [!IMPORTANT]
>  从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，可以设置段大小和最大第 0 代大小值大于`DWORD`通过使用[IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>参数  
 `SegmentSize`  
 [in]由垃圾回收系统段的大小。  
  
 `MaxGen0Size`  
 [in]第 0 代最大大小。  
  
## <a name="remarks"></a>备注  
 `SetGCStartupLimits`可能只有一次调用方法。 以后无法更改这些值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl GCHost.h  
  
 **库：** 包含为 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IGCHost 接口](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
