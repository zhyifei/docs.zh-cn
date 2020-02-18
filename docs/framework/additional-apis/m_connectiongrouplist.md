---
title: ServicePoint 字段 m_ConnectionGroupList
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
ms.openlocfilehash: f2759f82f335415edf7bab33edbd446eec6ffbb5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215521"
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
