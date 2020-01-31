---
title: ICorPublishProcess 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790543"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess 接口
提供用于访问要显示的有关进程的信息的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumAppDomains 方法](icorpublishprocess-enumappdomains-method.md)|获取一个[ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)实例，它包含此 `ICorPublishProcess`所引用的进程中的应用程序域。|  
|[GetDisplayName 方法](icorpublishprocess-getdisplayname-method.md)|获取此 `ICorPublishProcess`所引用的进程的可执行文件的完整路径。|  
|[GetProcessID 方法](icorpublishprocess-getprocessid-method.md)|获取此 `ICorPublishProcess`所引用的进程的操作系统标识符。|  
|[IsManaged 方法](icorpublishprocess-ismanaged-method.md)|获取一个值，该值指示此 `ICorPublishProcess` 引用的进程是否已知正在运行托管代码。|  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [CorpubPublish 组件类](corpubpublish-coclass.md)
