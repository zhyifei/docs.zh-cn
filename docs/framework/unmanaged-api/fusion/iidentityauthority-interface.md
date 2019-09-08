---
title: IIdentityAuthority 接口
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796425"
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority 接口

管理代码对象的标识键。

## <a name="methods"></a>方法

|方法|描述|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|获取一个值，该值指示两个指定的[IDefinitionIdentity](idefinitionidentity-interface.md)实例是否相等。|
|`IIdentityAuthority::AreReferencesEqual`|获取一个值，该值指示两个指定的[IReferenceIdentity](ireferenceidentity-interface.md)实例是否相等。|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|获取一个值，该值指示两个指定的字符串定义标识表示形式是否相等。|
|`IIdentityAuthority::AreTextualReferencesEqual`|获取一个值，该值指示两个指定的字符串引用标识表示形式是否相等。|
|`IIdentityAuthority::CreateDefinition`|获取一个指针，该指针`IDefinitionIdentity`指向表示当前范围内的代码对象的新实例。|
|`IIdentityAuthority::CreateReference`|获取一个指针，该指针`IReferenceIdentity`指向表示当前范围内的代码对象的新实例。|
|`IIdentityAuthority::DefinitionToText`|获取指定`IDefinitionIdentity`的格式化字符串版本。|
|`IIdentityAuthority::DefinitionToTextBuffer`|使用指定`IDefinitionIdentity`的字符串版本填充指定的宽字符缓冲区。|
|`IIdentityAuthority::DoesDefinitionMatchReference`|获取一个值，该值指示指定`IDefinitionIdentity`的和`IReferenceIdentity`实例是否引用同一代码对象。|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|获取一个值，该值指示指定的字符串是否引用同一代码对象。|
|`IIdentityAuthority::GenerateDefinitionKey`|获取一个指针，该指针指向指定`IDefinitionIdentity`的新创建的字符串键。|
|`IIdentityAuthority::GenerateReferenceKey`|获取一个指针，该指针指向指定`IReferenceIdentity`的新创建的字符串键。|
|`IIdentityAuthority::HashDefinition`|获取指定`IDefinitionIdentity`的的哈希值。|
|`IIdentityAuthority::HashReference`|获取指定`IReferenceIdentity`的的哈希值。|
|`IIdentityAuthority::ReferenceToText`|获取指定`IReferenceIdentity`的格式化字符串版本。|
|`IIdentityAuthority::ReferenceToTextBuffer`|使用指定`IReferenceIdentity`的字符串版本填充指定的宽字符缓冲区。|
|`IIdentityAuthority::TextToDefinition`|获取一个接口指针，该`IDefinitionIdentity`指针指向从指定的格式化字符串生成的实例。|
|`IIdentityAuthority::TextToReference`|获取一个接口指针，该`IReferenceIdentity`指针指向从指定的格式化字符串生成的实例。|

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../get-started/system-requirements.md)。

**标头：** 隔离。h

**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
