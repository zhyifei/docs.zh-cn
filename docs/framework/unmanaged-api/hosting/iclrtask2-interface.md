---
title: "ICLRTask2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f2312d193031eae556f55b061a36259531d013b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2-interface"></a>ICLRTask2 接口
提供的所有功能[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口; 此外，提供都了允许线程中止延迟，可将当前线程上的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginPreventAsyncAbort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|延迟新线程中止当前线程上的请求。|  
|[EndPreventAsyncAbort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|允许新的或挂起的线程中止请求导致线程中止当前线程上。|  
  
## <a name="remarks"></a>备注  
 `ICLRTask2`接口继承`ICLRTask`接口，并添加允许主机延迟线程中止，以防一定不能失败的代码区域的方法。 调用`BeginPreventAsyncAbort`递增的当前线程和调用的延迟线程中止计数器`EndPreventAsyncAbort`递减它。 调用`BeginPreventAsyncAbort`和`EndPreventAsyncAbort`可以嵌套。 只要计数器值大于零，当前线程的线程中止延迟。  
  
 如果调用`BeginPreventAsyncAbort`和`EndPreventAsyncAbort`不是成对，则可能会进入在哪个线程中止无法传送到当前线程的状态。  
  
 延迟将不接受中止本身一个线程。  
  
 虚拟机 (VM) 内部使用此功能公开的功能。 不正确使用了这些方法可能导致虚拟机中未指定的行为。 例如，调用`EndPreventAsyncAbort`而无需首先调用`BeginPreventAsyncAbort`VM 先前已增大时无法设置为零的计数器。 同样，内部计数器未检查存在溢出。 如果该阈值超过其整型的限制，因为它就会递增主机和 VM，获得的行为是未指定。  
  
 有关成员的信息从继承为`ICLRTask`和此接口的其他用法，请参阅[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
