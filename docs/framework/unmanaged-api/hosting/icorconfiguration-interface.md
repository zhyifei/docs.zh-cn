---
title: ICorConfiguration 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63699f0af69b3a7623c5e9da156c2ff8ae83ccfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437503"
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
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost 组件类](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
