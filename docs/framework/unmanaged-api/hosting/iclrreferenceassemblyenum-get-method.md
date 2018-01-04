---
title: "ICLRReferenceAssemblyEnum::Get 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRReferenceAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3cdf6a8eb761367d23e1ce61cd24727e7a3d6ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrreferenceassemblyenumget-method"></a>ICLRReferenceAssemblyEnum::Get 方法
获取所提供的索引处的程序集标识。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwIndex`  
 [in]要返回的程序集标识的从零开始的索引。  
  
 `pwzBuffer`  
 [out]包含程序集标识数据的缓冲区。  
  
 `pcchBufferSize`  
 [在中，out]大小`pwzBuffer`缓冲区。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`Get`已成功返回。|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer`对于太小。|  
|ERROR_NO_MORE_ITEMS|该枚举包含更多的项。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `Get`通常称为两次。 第一个调用提供的 null 值`pwzBuffer`，并将设置`pcchBufferSize`到适合的大小`pwzBuffer`。 第二个调用提供大小合适`pwzBuffer`，并包含完成后的规范的程序集标识数据。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRReferenceAssemblyEnum 接口](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
