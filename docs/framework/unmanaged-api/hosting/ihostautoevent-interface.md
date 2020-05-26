---
title: IHostAutoEvent 接口
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: a24939ac0b0808546ef3615fae4909c6c3cf8a2e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804995"
---
# <a name="ihostautoevent-interface"></a>IHostAutoEvent 接口
提供宿主自动重置事件的实现的表示形式。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[Set 方法](ihostautoevent-set-method.md)|将当前 `IHostAutoEvent` 实例设置为终止状态。|  
|[Wait 方法](ihostautoevent-wait-method.md)|导致当前 `IHostAutoEvent` 实例等待，直到事件拥有或经过指定的时间量。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRSyncManager 接口](iclrsyncmanager-interface.md)
- [IHostManualEvent 接口](ihostmanualevent-interface.md)
- [IHostSyncManager 接口](ihostsyncmanager-interface.md)
- [承载接口](hosting-interfaces.md)
