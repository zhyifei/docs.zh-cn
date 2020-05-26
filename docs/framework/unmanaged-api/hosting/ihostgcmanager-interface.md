---
title: IHostGCManager 接口
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804857"
---
# <a name="ihostgcmanager-interface"></a>IHostGCManager 接口
提供一些方法，这些方法用于通知由公共语言运行时（CLR）实现的垃圾回收机制中的事件宿主。  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|[SuspensionEnding 方法](ihostgcmanager-suspensionending-method.md)|通知宿主 CLR 正在继续执行已挂起垃圾回收的线程上的任务。|  
|[SuspensionStarting 方法](ihostgcmanager-suspensionstarting-method.md)|通知宿主 CLR 正在暂停执行任务，以执行垃圾回收。|  
|[ThreadIsBlockingForSuspension 方法](ihostgcmanager-threadisblockingforsuspension-method.md)|通知宿主从中发出方法调用的线程将要阻止垃圾回收。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRTask 接口](iclrtask-interface.md)
- [ICLRTaskManager 接口](iclrtaskmanager-interface.md)
- [IHostTask 接口](ihosttask-interface.md)
- [IHostTaskManager 接口](ihosttaskmanager-interface.md)
- [承载接口](hosting-interfaces.md)
