---
title: SqlChars.Stream 属性 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 7485f462ec19a20a4bc6989c2f1b576b0f991009
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634397"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="d11e8-102">SqlChars.Stream 属性</span><span class="sxs-lookup"><span data-stu-id="d11e8-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="d11e8-103">获取或设置字符流。</span><span class="sxs-lookup"><span data-stu-id="d11e8-103">Gets or sets the character stream.</span></span> <span data-ttu-id="d11e8-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="d11e8-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d11e8-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="d11e8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d11e8-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="d11e8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="d11e8-107">属性值</span><span class="sxs-lookup"><span data-stu-id="d11e8-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="d11e8-108">字符流中。</span><span class="sxs-lookup"><span data-stu-id="d11e8-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="d11e8-109">备注</span><span class="sxs-lookup"><span data-stu-id="d11e8-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d11e8-110">`SqlChars.Stream`属性内部使用并且不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="d11e8-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d11e8-111">Microsoft 不支持在生产应用程序在任何情况下使用此属性。</span><span class="sxs-lookup"><span data-stu-id="d11e8-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d11e8-112">要求</span><span class="sxs-lookup"><span data-stu-id="d11e8-112">Requirements</span></span>

<span data-ttu-id="d11e8-113">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d11e8-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d11e8-114">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="d11e8-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d11e8-115">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="d11e8-115">**.NET Framework versions:** Available since 2.0.</span></span>
