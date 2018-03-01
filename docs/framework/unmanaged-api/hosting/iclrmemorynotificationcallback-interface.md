---
title: "ICLRMemoryNotificationCallback 接口"
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
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc09e3668dc814360de0256c2476ffa7b61462ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback 接口
允许使用类似于 Win32 方法报告内存压力情况主机`CreateMemoryResourceNotification`函数。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[OnMemoryNotification 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|通知在计算机上的内存负载公共语言运行时 (CLR)。|  
  
## <a name="remarks"></a>备注  
 主机使用`ICLRMemoryNotificationCallback`接口来请求 CLR 释放内存资源。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
