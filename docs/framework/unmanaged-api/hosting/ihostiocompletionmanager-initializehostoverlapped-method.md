---
title: "IHostIoCompletionManager::InitializeHostOverlapped 方法"
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
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b558d638e598ba6e3d0055e3a842976896e99d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>IHostIoCompletionManager::InitializeHostOverlapped 方法
为宿主提供初始化任何自定义的数据，可将附加到 Win32 的机会`OVERLAPPED`用于异步 I/O 请求的结构。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pvOverlapped`  
 [in]一个指向 Win32`OVERLAPPED`结构要包含在 I/O 请求。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存的可用，无法分配请求的资源。|  
  
## <a name="remarks"></a>备注  
 Windows 平台函数使用`OVERLAPPED`结构，用于存储有关异步 I/O 请求的状态。 CLR 调用`InitializeHostOverlapped`方法以便为主机提供自定义将数据追加到机会`OVERLAPPED`实例。  
  
> [!IMPORTANT]
>  若要获取其自定义数据块的开头，主机必须设置偏移量的大小`OVERLAPPED`结构 (`sizeof(OVERLAPPED)`)。  
  
 返回值 E_OUTOFMEMORY 指示主机具有无法初始化其自定义数据。 在这种情况下，CLR 报告错误，并且无法进行调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRIoCompletionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [GetHostOverlappedSize 方法](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [IHostIoCompletionManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
