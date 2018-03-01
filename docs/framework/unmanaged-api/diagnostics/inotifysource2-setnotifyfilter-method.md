---
title: "INotifySource2::SetNotifyFilter 方法"
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
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bba34a9e28d1995ca04c7108ce33adc6e676b357
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysource2setnotifyfilter-method"></a>INotifySource2::SetNotifyFilter 方法
将分配与此源使用通知筛选器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
#### <a name="parameters"></a>参数  
 `in_NotifyFilter`  
 [in]按位组合[NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md)标识调试器 API 回调的枚举值。  
  
 `in_pUserThreadFilter`  
 [in]指向的指针[USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md)标识调试器 API 的线程的结构。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则为 S_OK。  
  
## <a name="requirements"></a>惠?  
 **标头：** ProtocolNotify2.idl  
  
## <a name="see-also"></a>请参阅  
 [INotifySource2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [INotifyConnection2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [INotifySink2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
