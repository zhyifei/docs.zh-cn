---
title: IDebuggerThreadControl 接口
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 619a28d2382aa9cc3130a3130c07fa1e283119e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437910"
---
# <a name="idebuggerthreadcontrol-interface"></a>IDebuggerThreadControl 接口
提供用于通知主机有关阻止和取消阻止的线程调试服务的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ThreadIsBlockingForDebugger 方法](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|通知正在发送此回调的线程即将主机到调试服务内的块。|  
|[ReleaseAllRuntimeThreads 方法](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|通知主机调试服务即将释放所有受阻的线程。|  
|[StartBlockingForDebugger 方法](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|通知主机调试服务即将开始阻止所有线程。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
