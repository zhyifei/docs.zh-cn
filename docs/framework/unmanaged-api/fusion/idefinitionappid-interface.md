---
title: IDefinitionAppId 接口
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108201"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId 接口
表示定义当前作用域中的应用程序的代码的唯一标识符。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|获取一个格式字符串，该字符串表示此 `IDefinitionAppId` 对象中的代码。|  
|`IDefinitionAppId::put_Codebase`|将此 `IDefinitionAppId` 对象的代码设置为指定的格式化字符串值。|  
|`IDefinitionAppId::EnumAppPath`|获取一个指向[IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md)对象的接口指针，该对象包含当前应用程序路径中的程序集。|  
|`IDefinitionAppId::SetAppPath`|将当前范围中的程序集的应用程序路径设置为指定的[IDefinitionIdentity](idefinitionidentity-interface.md)对象所引用的值。|  
|`IDefinitionAppId::get_SubscriptionId`|获取一个指针，该指针指向此 `IDefinitionAppId` 对象的订阅的标记标识符的字符串表示形式。|  
|`IDefinitionAppId::put_SubscriptionId`|将此 `IDefinitionAppId` 对象的订阅的标记标识符设置为指定的字符串值。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** 隔离。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
