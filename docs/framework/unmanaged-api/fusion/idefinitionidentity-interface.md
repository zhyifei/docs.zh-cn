---
title: IDefinitionIdentity 接口
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796521"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity 接口
表示定义当前作用域中的应用程序的代码的唯一签名。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|获取一个接口指针，该指针`IDefinitionIdentity`指向与此`IDefinitionIdentity`相同的新对象，但指定的特性更改除外。|  
|`IDefinitionIdentity::EnumAttributes`|获取一个指向[IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)对象的接口指针，该对象包含与此`IDefinitionIdentity`关联的特性。|  
|`IDefinitionIdentity::GetAttribute`|获取指定命名空间中具有指定名称的属性的值。|  
|`IDefinitionIdentity::SetAttribute`|将指定命名空间中具有指定名称的特性设置为指定值。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 隔离。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
