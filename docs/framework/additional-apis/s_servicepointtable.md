---
title: 服务点管理器.s_ServicePointTable字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155803"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>服务点管理器的服务\_点表字段

`ServicePointManager.s_ServicePointTable`是<xref:System.Collections.Hashtable>包含 中的活动 HTTP 连接的列表<xref:System.Net.ServicePoint>的<xref:System.AppDomain>。

## <a name="syntax"></a>语法
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> 该`ServicePointManager.s_ServicePointTable`字段是私有的，不应直接用于代码。
>
> 在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：**<xref:System.Net>

**装配：** 系统（系统中）

**.NET 框架版本：** 自 2.0 起可用。
