---
title: "ICLRIoCompletionManager::OnComplete 方法"
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
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6f933172e9de5aa18d880791c439d51cce919e83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a>ICLRIoCompletionManager::OnComplete 方法
进行调用的 I/O 请求的状态通知公共语言运行时 (CLR) [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwErrorCode`  
 [in]HRESULT 值，该值指示绑定操作的状态。  
  
-   则为 S_OK 表示该操作成功完成。  
  
-   HOST_E_INTERRUPTED 指示调用终止之前完成。  
  
-   E_FAIL 指示发生了未知的、 不可恢复的灾难性故障。  
  
 `NumberOfBytesTransferred`  
 [in]在处理 I/O 请求过程中传输的字节数。  
  
 `pvOverlapped`  
 [in]指向的指针`OVERLAPPED`结构传递给调用`IHostIoCompletionManager::Bind`方法。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`OnComplete`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 如果主机实现的 I/O 完成抽象，CLR 通过使用的方法进行输入/输出请求通过主机[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)。 主机然后调用`OnComplete`方法来通知运行时的此类请求的结果。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRIoCompletionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [IHostIoCompletionManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [IHostThreadPoolManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
