---
title: ICorPublishProcessEnum 接口
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 188ff8feabd704d828256a09aca20f9db2227f2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790497"
---
# <a name="icorpublishprocessenum-interface"></a>ICorPublishProcessEnum 接口
[ICorPublishEnum](icorpublishenum-interface.md)接口的子类，提供遍历[ICorPublishProcess](icorpublishprocess-interface.md)对象集合的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Next 方法](icorpublishprocessenum-next-method.md)|从当前位置开始，获取集合中指定数量的 `ICorPublishProcess` 实例。|  
  
## <a name="remarks"></a>备注  
 `ICorPublishProcessEnum` 接口实现抽象接口[ICorPublishEnum](icorpublishenum-interface.md)的方法。  
  
 `ICorPublishProcessEnum` 实例是通过[ICorPublish：： EnumProcesses](icorpublish-enumprocesses-method.md)方法创建的。 `ICorPublishProcess` 对象集合的遍历基于创建 `ICorPublishProcessEnum` 实例时给定的筛选条件。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [CorpubPublish 组件类](corpubpublish-coclass.md)
