---
title: SqlStreamChars.Read (Char []，Int32，Int32) 方法 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: df715f622f874b3c9297c421eab9f4c7504e696b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634323"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>SqlStreamChars.Read (Char []，Int32，Int32) 方法

当在派生类中重写，请从输入流读取下一组字符。 包含此方法的程序集具有与 SQLAccess.dll 友元关系。 它被用于 SQL server 上。 对于其他数据库，使用提供该数据库的宿主机制。

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>参数

`buffer`\
要读取的字符数组。

`offset`\
相对于源偏移量。

`count`\
要从当前流中读取的字符数。

## <a name="returns"></a>返回

<xref:System.Int32>\
读入缓冲区的总字符数。

## <a name="remarks"></a>备注

> [!WARNING]
> `SqlStreamChars.Read`方法是私有的不适合直接在代码中使用。
>
> Microsoft 不支持在生产应用程序在任何情况下使用此字段。

## <a name="requirements"></a>要求

**Namespace**：<xref:System.Data.SqlTypes>

**程序集：** System.Data （在 System.Data.dll 中)

**.NET framework 版本：** 自 2.0 之后可用。
