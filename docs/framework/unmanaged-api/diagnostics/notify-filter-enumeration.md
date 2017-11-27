---
title: "NOTIFY_FILTER 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NOTIFY_FILTER
api_location: diasymreader.dll
api_type: COM
f1_keywords: NOTIFY_FILTER
helpviewer_keywords: NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9db03458aab60d28efe52edfd9830da7862fcb8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="notifyfilter-enumeration"></a>NOTIFY_FILTER 枚举
标识调试器函数的回调。 有关详细信息，请参阅[inotifysource2:: Setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|指示[inotifysink2:: Onsynccallout](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)应该调用方法。|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|指示[inotifysink2:: Onsynccallenter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)应该调用方法。|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|指示[inotifysink2:: Onsynccallexit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)应该调用方法。|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|指示[inotifysink2:: Onsynccallreturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)应该调用方法。|  
|`NOTIFY_FILTER_ALLSYNC`|指示所有[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)应调用方法。|  
|`NOTIFY_FILTER_ALL`|激活所有现有和将来的通知。|  
|`NOTIFY_FILTER_NONE`|指示应调用任何通知方法。|  
  
## <a name="requirements"></a>要求  
 **标头：** ProtocolNotify2.idl  
  
## <a name="see-also"></a>另请参阅  
 [诊断符号存储区枚举](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
