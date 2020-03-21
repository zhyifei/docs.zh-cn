---
title: 连接组.m_ConnectionList字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
ms.openlocfilehash: 8eb6f215c36e214f7095eeba90bf0aed66dfcea0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155845"
---
# <a name="connectiongroupm_connectionlist-field"></a>连接组.m\_连接列表字段

`ConnectionGroup.m_ConnectionList`是一<xref:System.Collections.ArrayList>个连接对象，用于相同的 URI，并为某些其他属性（如过期和身份验证）共享相同的值。

## <a name="syntax"></a>语法
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> 该`ConnectionGroup.m_ConnectionList`字段是私有的，不应直接用于代码。
>
> 在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：**<xref:System.Net>

**装配：** 系统（系统中）

**.NET 框架版本：** 自 2.0 起可用。
