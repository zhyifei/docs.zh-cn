---
title: BodyToString 方法（System.servicemodel. 通道）
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 7b0b56bfda1c0c37f43f95e9684d3b4042c1b97c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451310"
---
# <a name="messagebodytostring-method"></a>BodyToString 方法

通过调用 <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> 方法，将消息正文转换为字符串。

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>参数

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  用于将消息正文转换为字符串的编写器。

## <a name="remarks"></a>备注

> [!WARNING]
> `Message.BodyToString` 方法是内部的，不应在代码中直接使用。
>
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。

## <a name="requirements"></a>要求

**命名空间：** <xref:System.ServiceModel.Channels>

**程序集：** System.servicemodel .dll

**.NET Framework 版本：** 自3.0 起可用。
