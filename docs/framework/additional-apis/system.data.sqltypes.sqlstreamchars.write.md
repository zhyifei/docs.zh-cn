---
title: SqlStreamChars.Write (Char []，Int32，Int32) 方法 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: dd9bb691f6d07f4875d684eef76d6329667003af
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221903"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>SqlStreamChars.Write (Char []，Int32，Int32) 方法

当在派生类中重写的字符序列写入当前流并将此流中的当前位置提升写入的字符数。 包含此方法的程序集具有与 SQLAccess.dll 友元关系。 它被用于 SQL server 上。 对于其他数据库，使用提供该数据库的宿主机制。

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>参数

`buffer`  
要写入的字符数组。

`offset`  
相对于源偏移量。

`count`  
要写入当前流的字符数。

## <a name="remarks"></a>备注

> [!WARNING]
> `SqlStreamChars.Write`方法是私有的不适合直接在代码中使用。
>
> Microsoft 不支持在生产应用程序在任何情况下使用此字段。

## <a name="requirements"></a>要求

**Namespace**：<xref:System.Data.SqlTypes>

**程序集：** System.Data （在 System.Data.dll 中)

**.NET framework 版本：** 自 2.0 之后可用。