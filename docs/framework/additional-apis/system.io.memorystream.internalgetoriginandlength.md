---
title: MemoryStream. InternalGetOriginAndLength 方法（System.IO）
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284041"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>MemoryStream. InternalGetOriginAndLength 方法

获取内存流的源的内部值和长度。

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>参数

- `origin` <xref:System.Int32>\
  此方法返回时，创建新 <xref:System.IO.MemoryStream> 对象时指定的字节数组的偏移量。 如果字节数组由 <xref:System.IO.MemoryStream>创建，则包含0。

- `length` <xref:System.Int32>\
  此方法返回时，为内存流中的字节数。

## <a name="remarks"></a>备注

> [!WARNING]
> `MemoryStream.InternalGetOriginAndLength` 方法是内部的，不应在代码中直接使用。
>
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。

## <a name="requirements"></a>要求

**命名空间：** <xref:System.IO>

**Assembly：** mscorlib （在 mscorlib.dll 中）

**.NET framework 版本**：自 2.0 之后可用。
