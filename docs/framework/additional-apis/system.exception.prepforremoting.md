---
title: PrepForRemoting 方法（系统）
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214887"
---
# <a name="exceptionprepforremoting-method"></a>Exception.PrepForRemoting 方法

保留服务器端堆栈跟踪，方法是将其追加到消息，然后在客户端调用站点重新引发异常。

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>返回

<xref:System.Exception>  
此 <xref:System.Exception> 实例。

## <a name="remarks"></a>备注

> [!WARNING]
> `Exception.PrepForRemoting` 方法是内部的，不应在代码中直接使用。
>
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。

## <a name="requirements"></a>要求

**命名空间：** <xref:System>

**Assembly：** mscorlib （在 mscorlib.dll 中）

**.NET Framework 版本：** 自1.0 起可用。
