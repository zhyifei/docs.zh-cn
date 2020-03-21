---
title: 服务点.m_ConnectionGroupList字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
ms.openlocfilehash: 2b1b46085ed035b67fd01447727b406fe3895980
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155890"
---
# <a name="servicepointm_connectiongrouplist-field"></a>服务点.m\_连接组列表字段

`ServicePoint.m_ConnectionGroupList`是连接<xref:System.Collections.Hashtable>组，每个组都持有<xref:System.Net.ServicePoint>URI 的连接。

## <a name="syntax"></a>语法
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> 该`ServicePoint.m_ConnectionGroupList`字段是私有的，不应直接用于代码。
>
> 在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：**<xref:System.Net>

**装配：** 系统（系统中）

**.NET 框架版本：** 自 2.0 起可用。
