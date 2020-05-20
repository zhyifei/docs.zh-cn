---
title: ICLRIoCompletionManager 接口
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703561"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager 接口
实现一个回调方法，该方法允许宿主向公共语言运行时（CLR）通知指定 i/o 请求的状态。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[OnComplete 方法](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|使用对[IHostIoCompletionManager：： Bind](ihostiocompletionmanager-bind-method.md)方法的调用，将发出的 i/o 请求状态通知给 CLR。|  
  
## <a name="remarks"></a>备注  
 宿主通过使用[IHostIoCompletionManager](ihostiocompletionmanager-interface.md)接口实现 i/o 完成抽象。 CLR 通过此接口发出 i/o 请求，主机使用接口通知运行时此类请求的结果 `ICLRIoCompletionManager` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IHostIoCompletionManager 接口](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager 接口](ihostthreadpoolmanager-interface.md)
- [承载接口](hosting-interfaces.md)
