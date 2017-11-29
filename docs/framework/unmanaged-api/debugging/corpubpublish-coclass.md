---
title: CorpubPublish Coclass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c1565c9321e64536139e02b239fbeb4247a58a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corpubpublish-coclass"></a>CorpubPublish 组件类
提供用于发布应用程序域和进程相关信息的接口。  
  
## <a name="syntax"></a>语法  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>接口  
  
|接口|描述|  
|---------------|-----------------|  
|[ICorPublish 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|提供有关进程和应用程序域的信息发布到这些进程的方法。|  
|[ICorPublishAppDomain 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|表示，并提供关于，应用程序域的过程中的信息。|  
|[ICorPublishAppDomainEnum 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|提供遍历进程中当前存在的应用程序域的集合的方法。|  
|[ICorPublishProcess 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|表示在计算机运行的进程。|  
|[ICorPublishProcessEnum 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|提供遍历集合的计算机运行的进程的方法。|  
  
## <a name="remarks"></a>备注  
 典型的发布方案涉及的开发人员想要调试应用程序域内的计算机运行的托管的代码。 宿主环境可能运行的进程中的多个应用程序域。 开发人员想要使用图形用户界面或某种其他方式来列出所有的计算机，运行的进程并选取一个特定的进程。 该列表应包括所有正在运行托管的代码的进程内的应用程序域。 然后，开发人员可以标识特定的应用程序域，并将调试器附加到该域。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
