---
title: IGCHost 接口
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
ms.openlocfilehash: 91483d5bdf1eb8e6b03d7691e2a95074e3789317
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134881"
---
# <a name="igchost-interface"></a>IGCHost 接口
提供一些方法，用于获取有关垃圾回收系统的信息并控制垃圾回收的某些方面。  
  
> [!NOTE]
> 从 .NET Framework 4.5 开始，可以使用[IGCHost2：： SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法将垃圾回收段的大小和垃圾回收系统的0代0的最大大小设置为大于 `DWORD` 限制的值。这是由[SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)方法强制实施的。  
  
> [!NOTE]
> 此接口仅供专家使用。 如果使用不当，可能会影响应用程序的性能。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Collect 方法](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|为给定的生成强制执行回收，而不考虑当前垃圾回收的状态。|  
|[GetStats 方法](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|获取垃圾收集系统的当前状态的统计信息。|  
|[GetThreadStats 方法](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|获取用于垃圾回收的每个线程的统计信息。|  
|[SetGCStartupLimits 方法](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|设置第0代的段大小和最大大小。|  
|[SetVirtualMemLimit 方法](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|设置运行时的虚拟内存的最大大小。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost，GCHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost 组件类](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
