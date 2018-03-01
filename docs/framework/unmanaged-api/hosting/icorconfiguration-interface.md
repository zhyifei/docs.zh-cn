---
title: "ICorConfiguration 接口"
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
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af9a7d4bb1d38fd4a81e954074b074325409ee5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration 接口
提供用于配置公共语言运行时 (CLR) 方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[AddDebuggerSpecialThread 方法](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|指示应允许特定线程继续执行而调试器具有应用程序在托管或非托管调试方案期间停止调试服务。|  
|[SetDebuggerThreadControl 方法](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|设置调试服务将调用 CLR 线程阻止和解除阻止以用于调试的回调接口。|  
|[SetGCHostControl 方法](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|设置要用于通过垃圾回收器请求主机后，若要更改的虚拟内存限制的回调接口。|  
|[SetGCThreadControl 方法](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|设置计划对于非运行时任务，否则会阻止垃圾回收的线程使用的回调的接口。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost 组件类](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
