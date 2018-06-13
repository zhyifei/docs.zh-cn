---
title: ICLRGCManager 接口
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045b924033630ea98d5a532a62f1037a5972df90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433919"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager 接口
提供允许的主机与公共语言运行时的垃圾回收系统进行交互的方法。  
  
> [!NOTE]
>  从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，你可以使用[iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法设置为值的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小更大比`DWORD`施加的限制， [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Collect 方法](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|强制指定代的垃圾回收。|  
|[GetStats 方法](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|获取一组有关垃圾回收系统的当前统计信息。|  
|[SetGCStartupLimits 方法](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|设置的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。|  
  
## <a name="remarks"></a>备注  
 公共语言运行时 (CLR) 实现与托管其垃圾回收机制<xref:System.GC>类型。 有关垃圾回收系统的详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [自动内存管理](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS 结构](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [CLR Hosting 接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
