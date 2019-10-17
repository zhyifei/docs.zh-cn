---
title: SqlStreamChars 属性（SqlTypes）
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
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395732"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="2d85c-102">SqlStreamChars 属性</span><span class="sxs-lookup"><span data-stu-id="2d85c-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="2d85c-103">当在派生类中重写时，获取一个值，该值指示流是否 `null`。</span><span class="sxs-lookup"><span data-stu-id="2d85c-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="2d85c-104">包含此属性的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="2d85c-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="2d85c-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="2d85c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="2d85c-106">对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="2d85c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d85c-107">语法</span><span class="sxs-lookup"><span data-stu-id="2d85c-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="2d85c-108">属性值</span><span class="sxs-lookup"><span data-stu-id="2d85c-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="2d85c-109">如果流 @no__t，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="2d85c-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d85c-110">备注</span><span class="sxs-lookup"><span data-stu-id="2d85c-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="2d85c-111">@No__t-0 属性是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="2d85c-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2d85c-112">在任何情况下，Microsoft 不支持在生产应用程序中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="2d85c-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d85c-113">要求</span><span class="sxs-lookup"><span data-stu-id="2d85c-113">Requirements</span></span>

<span data-ttu-id="2d85c-114">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="2d85c-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="2d85c-115">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="2d85c-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="2d85c-116">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="2d85c-116">**.NET Framework versions:** Available since 2.0.</span></span>
