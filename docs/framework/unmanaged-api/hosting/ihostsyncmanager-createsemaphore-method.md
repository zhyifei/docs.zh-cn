---
title: IHostSyncManager::CreateSemaphore 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 02066d3923714e66bf287f1435b7854280c97cb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195834"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a>IHostSyncManager::CreateSemaphore 方法
创建公共语言运行时（CLR）的[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)对象，以用作等待事件的信号量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwInitial`  
 中`ppSemaphore`的初始计数。  
  
 `dwMax`  
 中`ppSemaphore`的最大计数。  
  
 `ppSemaphore`  
 弄指向 `IHostSemaphore` 实例的地址的指针; 如果无法创建信号量，则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`CreateSemaphore` 成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存可用于创建请求的事件对象。|  
  
## <a name="remarks"></a>备注  
 `CreateSemaphore` 镜像同名的 Win32 函数。 `dwInitial` 和 `dwMax` 参数分别使用与 Win32 `lInitialCount` 和 `lMaximumCount` 参数相同的信号量计数语义。 `dwInitial` 必须介于零和 `dwMax`（含）之间。 `dwMax` 必须大于零。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSemaphore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [IHostSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
