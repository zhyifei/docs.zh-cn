---
title: 连接.m_WriteList字段
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
ms.openlocfilehash: 6c60831ddf23ce8ac9afcf244383d24732c3ef8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155832"
---
# <a name="connectionm_writelist-field"></a>连接.m\_写入列表字段

`Connection.m_WriteList`<xref:System.Collections.ArrayList>是排队通过<xref:System.Net.HttpWebRequest>HTTP 发送的对象。

## <a name="syntax"></a>语法
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> 该`Connection.m_WriteList`字段是私有的，不应直接用于代码。
>
> 在任何情况下，Microsoft 都不支持在生产应用程序中使用此字段。

## <a name="requirements"></a>要求

**命名空间：**<xref:System.Net>

**装配：** 系统（系统中）

**.NET 框架版本：** 自 2.0 起可用。
