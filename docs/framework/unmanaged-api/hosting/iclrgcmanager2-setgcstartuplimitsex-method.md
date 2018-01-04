---
title: "ICLRGCManager2::SetGCStartupLimitsEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 371d6d32b3f9f5da0411234438972a8d2df4cc3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a>ICLRGCManager2::SetGCStartupLimitsEx 方法
设置的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>参数  
 `SegmentSize`  
 [in]垃圾回收段指定的大小。  
  
 最小的段大小为 4 MB。 段可以增加增量为 1 MB 或更大。  
  
 `MaxGen0Size`  
 [in]第 0 代指定最大大小。  
  
 最小的第 0 代大小为 64 KB。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimitsEx`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 值的`SetGCStartupLimitsEx`仅之前启动主机时，可以指定集。 更高版本调用`SetGCStartupLimitsEx`将被忽略。  
  
 若要设置而不会影响另两个参数中，你不想要更改的参数指定 0 （零）。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [自动内存管理](../../../../docs/standard/automatic-memory-management.md)  
 [垃圾回收](../../../../docs/standard/garbage-collection/index.md)  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRGCManager2 接口](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
