---
title: EnumImportTypes 方法
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cd154ac90418dd0f6f476151686ff670c01c98c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632237"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes 方法

枚举每个作用域中的每个类型。

## <a name="syntax"></a>语法

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>参数

`hEnum`\
枚举器的句柄。

`dwMax`\
要检索的类型的最大数目。

`aTypeDefs`\
收到令牌类型，不能超过`dwMax`。

`pdwCount`\
接收中的类型的实际数目`aTypeDefs`。

## <a name="return-value"></a>返回值

如果该方法成功，返回，则为 S_OK。

## <a name="requirements"></a>要求

需要 alink.h

## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
