---
title: "ICorPublishProcess 接口"
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
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 765be4e0ae7657d169ea561bc6a36bcf8cc11153
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess 接口
提供访问要显示有关进程的信息的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumAppDomains 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|获取[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)实例，其中包含在引用此过程中的应用程序域`ICorPublishProcess`。|  
|[GetDisplayName 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|获取引用此进程可执行文件的完整路径`ICorPublishProcess`。|  
|[GetProcessID 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|获取引用此进程的操作系统识别符`ICorPublishProcess`。|  
|[IsManaged 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|获取一个值，该值指示由此是否引用的进程`ICorPublishProcess`已知运行托管的代码。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl、 CorPub.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [CorpubPublish 组件类](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
