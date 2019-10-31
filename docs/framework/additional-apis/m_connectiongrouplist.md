---
title: ServicePoint. m_ConnectionGroupList 字段
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1991dae4d03f617857b860f920077531f7937bf1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120051"
---
# <a name="servicepointm_connectiongrouplist-field"></a>ServicePoint\_ConnectionGroupList 字段

`ServicePoint.m_ConnectionGroupList` 是连接组的 <xref:System.Collections.Hashtable>，每个组都具有 <xref:System.Net.ServicePoint>URI 的连接。

## <a name="syntax"></a>语法
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> `ServicePoint.m_ConnectionGroupList` 字段是专用的，不应在代码中直接使用。
> 
> 在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：** <xref:System.Net>

**程序集：** 系统（在 System.web 中）

**.NET Framework 版本：** 自2.0 起可用。
