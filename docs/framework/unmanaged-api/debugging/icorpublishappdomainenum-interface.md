---
title: ICorPublishAppDomainEnum 接口
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790666"
---
# <a name="icorpublishappdomainenum-interface"></a>ICorPublishAppDomainEnum 接口
[ICorPublishEnum](icorpublishenum-interface.md)接口的子类，它提供了用于遍历进程中当前存在的[ICorPublishAppDomain](icorpublishappdomain-interface.md)对象的集合的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Next 方法](icorpublishappdomainenum-next-method.md)|从当前位置开始，获取集合中指定数量的 `ICorPublishAppDomain` 实例。|  
  
## <a name="remarks"></a>备注  
 `ICorPublishAppDomainEnum` 接口实现抽象接口[ICorPublishEnum](icorpublishenum-interface.md)的方法。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [CorpubPublish 组件类](corpubpublish-coclass.md)
