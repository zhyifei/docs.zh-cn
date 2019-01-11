---
title: SqlStreamChars.CanSeek 属性 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8d7bd7fb90177932b413c379f618a6d36374de57
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223138"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="17f72-102">SqlStreamChars.CanSeek 属性</span><span class="sxs-lookup"><span data-stu-id="17f72-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="17f72-103">当在派生类中重写，获取一个值，该值指示当前流是否支持查找操作。</span><span class="sxs-lookup"><span data-stu-id="17f72-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="17f72-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="17f72-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="17f72-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="17f72-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="17f72-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="17f72-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="17f72-107">属性值</span><span class="sxs-lookup"><span data-stu-id="17f72-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="17f72-108">`true` 如果当前流支持查找操作;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="17f72-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="17f72-109">备注</span><span class="sxs-lookup"><span data-stu-id="17f72-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="17f72-110">`SqlStreamChars.CanSeek`属性是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="17f72-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="17f72-111">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="17f72-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="17f72-112">要求</span><span class="sxs-lookup"><span data-stu-id="17f72-112">Requirements</span></span>

<span data-ttu-id="17f72-113">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="17f72-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="17f72-114">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="17f72-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="17f72-115">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="17f72-115">**.NET Framework versions:** Available since 2.0.</span></span>