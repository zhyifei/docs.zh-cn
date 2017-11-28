---
title: "IGCHost::SetGCStartupLimits 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.SetGCStartupLimits
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f95e5afa1297602e4ef12ed0dfb3f98aa5c762ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits 方法
为第 0 代中设置的段大小和最大大小。  
  
> [!IMPORTANT]
>  从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、 可以设置段大小和最大第 0 代大小值大于`DWORD`使用[igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>参数  
 `SegmentSize`  
 [in]由垃圾回收系统段的大小。  
  
 `MaxGen0Size`  
 [in]第 0 代最大大小。  
  
## <a name="remarks"></a>备注  
 `SetGCStartupLimits`可能一次调用方法。 以后无法更改这些值。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl、 GCHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IGCHost 接口](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
