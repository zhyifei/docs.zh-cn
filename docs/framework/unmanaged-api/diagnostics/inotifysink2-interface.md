---
title: INotifySink2 接口
ms.date: 03/30/2017
api_name:
- INotifySink2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2
helpviewer_keywords:
- INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f5307ce00160bb4151a7559daac4724367c6497
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157725"
---
# <a name="inotifysink2-interface"></a>INotifySink2 接口
声明用于接收器通知的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[OnSyncCallEnter 方法](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|输入调用时调用。|  
|[OnSyncCallExit 方法](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|退出调用时调用。|  
|[OnSyncCallOut 方法](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|调用超时时被调用。|  
|[OnSyncCallReturn 方法](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|当调用返回时调用。|  
  
## <a name="requirements"></a>要求  
 **标头：** ProtocolNotify2.idl  
  
## <a name="see-also"></a>请参阅

- [INotifyConnection2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [INotifySource2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
