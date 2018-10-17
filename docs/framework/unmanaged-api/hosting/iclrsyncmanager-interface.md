---
title: ICLRSyncManager 接口
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21295268ba5c230062fadddc9c61217f3574551b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49370979"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager 接口
定义允许主机以获取有关请求的任务的信息并在其同步实现检测死锁的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator 方法](iclrsyncmanager-createrwlockowneriterator-method.md)|公共语言运行时 (CLR) 创建主机，用于确定读取器 / 编写器锁等待的任务集的迭代器的请求。|  
|[DeleteRWLockOwnerIterator 方法](iclrsyncmanager-deleterwlockowneriterator-method.md)|请求 CLR 销毁一个迭代器，通过调用创建`CreateRWLockOwnerIterator`。|  
|[GetMonitorOwner 方法](iclrsyncmanager-getmonitorowner-method.md)|获取拥有指定的监视器的任务。|  
|[GetRWLockOwnerNext 方法](iclrsyncmanager-getrwlockownernext-method.md)|获取在当前的读取器 / 编写器锁等待下一个任务。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.Thread>  
 [IHostSyncManager 接口](ihostsyncmanager-interface.md)  
 [托管和非托管线程处理](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))  
 [承载接口](hosting-interfaces.md)
