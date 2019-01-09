---
title: SqlChars.Stream 属性 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: f8b6f4f3a92f1d78e434263c6a7897641867c412
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152600"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="2fede-102">SqlChars.Stream 属性</span><span class="sxs-lookup"><span data-stu-id="2fede-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="2fede-103">获取或设置字符流。</span><span class="sxs-lookup"><span data-stu-id="2fede-103">Gets or sets the character stream.</span></span> <span data-ttu-id="2fede-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="2fede-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="2fede-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="2fede-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="2fede-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="2fede-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="2fede-107">属性值</span><span class="sxs-lookup"><span data-stu-id="2fede-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="2fede-108">字符流中。</span><span class="sxs-lookup"><span data-stu-id="2fede-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fede-109">备注</span><span class="sxs-lookup"><span data-stu-id="2fede-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="2fede-110">`SqlChars.Stream`属性内部使用并且不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="2fede-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2fede-111">Microsoft 不支持在生产应用程序在任何情况下使用此属性。</span><span class="sxs-lookup"><span data-stu-id="2fede-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2fede-112">要求</span><span class="sxs-lookup"><span data-stu-id="2fede-112">Requirements</span></span>

<span data-ttu-id="2fede-113">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="2fede-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="2fede-114">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="2fede-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="2fede-115">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="2fede-115">**.NET Framework versions:** Available since 2.0.</span></span>