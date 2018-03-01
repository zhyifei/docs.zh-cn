---
title: "Connection.m_WriteList 字段"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e3849fdd327923e480cd88c932cfdce6580d3f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="connectionmwritelist-field"></a>Connection.m\_WriteList 字段

`Connection.m_WriteList`是<xref:System.Collections.ArrayList>的<xref:System.Net.HttpWebRequest>排队等待通过 HTTP 发送的对象。

## <a name="syntax"></a>语法
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> `Connection.m_WriteList`字段是私有，且不是在你的代码中直接使用。
> 
> Microsoft 不支持在生产应用程序在任何情况下使用此字段。

## <a name="requirements"></a>惠?

**Namespace:**<xref:System.Net>

**程序集：**系统 （在 System.dll)

**.NET framework 版本：**自 2.0 之后可用。
