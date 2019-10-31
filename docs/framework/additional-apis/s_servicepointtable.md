---
title: ServicePointManager. s_ServicePointTable 字段
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120004"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager\_ServicePointTable 字段

`ServicePointManager.s_ServicePointTable` 是包含 <xref:System.AppDomain>中的活动 HTTP 连接（<xref:System.Net.ServicePoint>）列表的 <xref:System.Collections.Hashtable>。

## <a name="syntax"></a>语法
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> `ServicePointManager.s_ServicePointTable` 字段是专用的，不应在代码中直接使用。
> 
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：** <xref:System.Net>

**程序集：** 系统（在 System.web 中）

**.NET Framework 版本：** 自2.0 起可用。
