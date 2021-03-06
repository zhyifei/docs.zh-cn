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
ms.openlocfilehash: 76a50be6da790ed7bd193c489d36e2823cdbe587
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616952"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager 接口
提供允许主机与公共语言运行时的垃圾回收系统交互的方法。  
  
> [!NOTE]
> 从 .NET Framework 4.5 开始，你可以使用[ICLRGCManager2：： SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法将垃圾回收段的大小和垃圾回收系统的第0代的最大大小设置为大于 `DWORD` [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md)方法施加的限制的值。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[Collect 方法](iclrgcmanager-collect-method.md)|强制执行指定代的垃圾回收。|  
|[GetStats 方法](iclrgcmanager-getstats-method.md)|获取有关垃圾回收系统的当前统计信息集。|  
|[SetGCStartupLimits 方法](iclrgcmanager-setgcstartuplimits-method.md)|设置垃圾回收段的大小以及垃圾回收系统的第0代的最大大小。|  
  
## <a name="remarks"></a>备注  
 公共语言运行时（CLR）实现了托管类型的垃圾回收机制 <xref:System.GC> 。 有关垃圾回收系统的详细信息，请参阅[垃圾](../../../standard/garbage-collection/index.md)回收。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [自动内存管理](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS 结构](cor-gc-stats-structure.md)
- [ICLRControl 接口](iclrcontrol-interface.md)
- [CLR 承载接口](clr-hosting-interfaces.md)
- [承载接口](hosting-interfaces.md)
- [承载](index.md)
