---
title: "INotifyConnection2::RegisterNotifySource 方法"
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
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a141872dc5699e5b317b21f03672fe0d76096392
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inotifyconnection2registernotifysource-method"></a>INotifyConnection2::RegisterNotifySource 方法
安装指定的通知源。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
#### <a name="parameters"></a>参数  
 `in_pNotifySource`  
 [in]指定要用作通知源的对象。  
  
 `out_ppNotifySink`  
 [out]接收要用作通知接收器的对象。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则为 S_OK。  
  
## <a name="requirements"></a>惠?  
 **标头：** ProtocolNotify2.idl  
  
## <a name="see-also"></a>请参阅  
 [INotifyConnection2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [INotifySource2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [INotifySink2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [UnregisterNotifySource 方法](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
