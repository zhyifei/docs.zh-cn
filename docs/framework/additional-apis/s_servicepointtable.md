---
title: ServicePointManager.s_ServicePointTable 字段
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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 5450a0cb3e5bd39a86365b16d372c7e573a43496
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable 字段

`ServicePointManager.s_ServicePointTable` 是<xref:System.Collections.Hashtable>其中包含的活动的 HTTP 连接的列表 (<xref:System.Net.ServicePoint>s) 中<xref:System.AppDomain>。

## <a name="syntax"></a>语法
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> `ServicePointManager.s_ServicePointTable`字段是私有，且不是在你的代码中直接使用。
> 
> Microsoft 不支持在生产应用程序在任何情况下使用此字段。

## <a name="requirements"></a>要求

**Namespace:** <xref:System.Net>

**程序集：**系统 （在 System.dll)

**.NET framework 版本：**自 2.0 之后可用。
