---
title: IHostCrst 接口
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130529"
---
# <a name="ihostcrst-interface"></a>IHostCrst 接口
用作线程的关键部分的宿主表示形式。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Enter 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|输入临界区。|  
|[Leave 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|离开临界区。|  
|[SetSpinCount 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|设置临界区的旋转计数。|  
|[TryEnter 方法](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|尝试输入临界区，并立即报告成功或失败。|  
  
## <a name="remarks"></a>备注  
 `IHostCrst` 允许公共语言运行时（CLR）与关键节的主机表示形式直接通信，而不是使用 `EnterCriticalSection` 或 `LeaveCriticalSection`等 Win32 函数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
