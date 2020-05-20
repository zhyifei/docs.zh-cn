---
title: ICLRReferenceAssemblyEnum::Get 方法
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
ms.openlocfilehash: 5afa7b37b804b6a11a894e0e6c7708c7787a20ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703362"
---
# <a name="iclrreferenceassemblyenumget-method"></a>ICLRReferenceAssemblyEnum::Get 方法
获取所提供索引处的程序集标识。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwIndex`  
 中要返回的程序集标识的从零开始的索引。  
  
 `pwzBuffer`  
 弄包含程序集标识数据的缓冲区。  
  
 `pcchBufferSize`  
 [in，out]缓冲区的大小 `pwzBuffer` 。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`Get`已成功返回。|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer` 太小。|  
|ERROR_NO_MORE_ITEMS|枚举中没有更多的项。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `Get`通常称为两次。 第一次调用为提供 null 值 `pwzBuffer` ，并将设置 `pcchBufferSize` 为适合的大小 `pwzBuffer` 。 第二个调用提供适当大小的 `pwzBuffer` ，并在完成时包含规范程序集标识数据。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRAssemblyReferenceList 接口](iclrassemblyreferencelist-interface.md)
- [ICLRReferenceAssemblyEnum 接口](iclrreferenceassemblyenum-interface.md)
