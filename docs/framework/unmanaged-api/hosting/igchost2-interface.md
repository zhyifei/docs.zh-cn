---
title: IGCHost2 接口
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6cbf44bd02a45b9b99d2dad63fc5bd6219c4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437672"
---
# <a name="igchost2-interface"></a>IGCHost2 接口
提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。  
  
> [!NOTE]
>  对于新开发，我们建议你使用[ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)接口。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[SetGCStartupLimitsEx 方法](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|为第 0 代中设置的段大小和最大大小。 使第 0 代和段大小大于`DWORD`。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl、 GCHost.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CLR Hosting 接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [CorRuntimeHost 组件类](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
