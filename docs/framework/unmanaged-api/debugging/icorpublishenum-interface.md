---
title: ICorPublishEnum 接口
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103452"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum 接口
用作枚举器的抽象基接口，这些枚举器用于发布有关进程和应用程序域的信息。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Clone 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|创建此 `ICorPublishEnum` 对象的副本。|  
|[GetCount 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|获取枚举中的项数。|  
|[Reset 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|将光标移到枚举的开头。|  
|[Skip 方法](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|按指定的项数在枚举中向前移动光标。|  
  
## <a name="remarks"></a>备注  
 以下枚举器派生自 `ICorPublishEnum`：  
  
- [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [CorpubPublish 组件类](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
