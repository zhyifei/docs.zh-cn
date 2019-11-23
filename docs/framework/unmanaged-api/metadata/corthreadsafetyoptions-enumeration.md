---
title: CorThreadSafetyOptions 枚举
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 93dd8c56176890d04d792f3c336492e4f232825b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442466"
---
# <a name="corthreadsafetyoptions-enumeration"></a>CorThreadSafetyOptions 枚举

指定用于选择线程安全性选项的标志。

## <a name="syntax"></a>语法

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a>Members

|成员|描述|
|------------|-----------------|
|`MDThreadSafetyDefault`|默认值。 与 `MDThreadSafetyOff` 相同。|
|`MDThreadSafetyOff`|Indicates that a reader/writer lock cannot be set.|
|`MDThreadSafetyOn`|Indicates that a reader/writer lock can be set.|

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。

**Header:** CorHdr.h

**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
