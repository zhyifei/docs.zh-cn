---
title: SqlStreamChars.IsNull 属性 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ec00b0afa1597c3ae6488c12fe5a0667dad70e2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675216"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="0a5ab-102">SqlStreamChars.IsNull 属性</span><span class="sxs-lookup"><span data-stu-id="0a5ab-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="0a5ab-103">当在派生类中重写时获取一个值，指示流是否`null`。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="0a5ab-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="0a5ab-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="0a5ab-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="0a5ab-107">语法</span><span class="sxs-lookup"><span data-stu-id="0a5ab-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="0a5ab-108">属性值</span><span class="sxs-lookup"><span data-stu-id="0a5ab-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="0a5ab-109">`true` 如果流已`null`; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a5ab-110">备注</span><span class="sxs-lookup"><span data-stu-id="0a5ab-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0a5ab-111">`SqlStreamChars.IsNull`属性是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0a5ab-112">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a5ab-113">要求</span><span class="sxs-lookup"><span data-stu-id="0a5ab-113">Requirements</span></span>

<span data-ttu-id="0a5ab-114">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="0a5ab-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="0a5ab-115">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="0a5ab-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="0a5ab-116">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="0a5ab-116">**.NET Framework versions:** Available since 2.0.</span></span>