---
title: SqlStreamChars.Length 属性 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c2ef66fa493512e1fa062e22858ea251ced39453
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705839"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="84958-102">SqlStreamChars.Length 属性</span><span class="sxs-lookup"><span data-stu-id="84958-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="84958-103">当在派生类中重写时获取当前流的长度。</span><span class="sxs-lookup"><span data-stu-id="84958-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="84958-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="84958-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="84958-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="84958-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="84958-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="84958-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="84958-107">语法</span><span class="sxs-lookup"><span data-stu-id="84958-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="84958-108">属性值</span><span class="sxs-lookup"><span data-stu-id="84958-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="84958-109">流的长度。</span><span class="sxs-lookup"><span data-stu-id="84958-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="84958-110">备注</span><span class="sxs-lookup"><span data-stu-id="84958-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="84958-111">`SqlStreamChars.Length`属性是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="84958-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="84958-112">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="84958-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="84958-113">要求</span><span class="sxs-lookup"><span data-stu-id="84958-113">Requirements</span></span>

<span data-ttu-id="84958-114">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="84958-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="84958-115">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="84958-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="84958-116">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="84958-116">**.NET Framework versions:** Available since 2.0.</span></span>