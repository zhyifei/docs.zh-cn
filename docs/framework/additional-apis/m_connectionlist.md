---
title: ConnectionGroup. m_ConnectionList 字段
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a06e535c554f765161d619d97f2e70072fbd0d5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120007"
---
# <a name="connectiongroupm_connectionlist-field"></a>ConnectionGroup\_ConnectionList 字段

`ConnectionGroup.m_ConnectionList` 是为同一 URI 提供服务的连接对象 <xref:System.Collections.ArrayList>，并为到期和身份验证等其他某些属性共享相同的值。

## <a name="syntax"></a>语法
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> `ConnectionGroup.m_ConnectionList` 字段是专用的，不应在代码中直接使用。
> 
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：** <xref:System.Net>

**程序集：** 系统（在 System.web 中）

**.NET Framework 版本：** 自2.0 起可用。
