---
title: SqlStreamChars. SetLength （Int64）方法（SqlTypes）
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395727"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="94588-102">SqlStreamChars. SetLength （Int64）方法</span><span class="sxs-lookup"><span data-stu-id="94588-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="94588-103">当在派生类中重写时，释放流使用的资源。</span><span class="sxs-lookup"><span data-stu-id="94588-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="94588-104">包含此方法的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="94588-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="94588-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="94588-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="94588-106">对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="94588-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="94588-107">参数</span><span class="sxs-lookup"><span data-stu-id="94588-107">Parameters</span></span>

`value`\
<span data-ttu-id="94588-108">所需的当前流的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="94588-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="94588-109">备注</span><span class="sxs-lookup"><span data-stu-id="94588-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="94588-110">@No__t-0 方法是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="94588-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="94588-111">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="94588-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="94588-112">要求</span><span class="sxs-lookup"><span data-stu-id="94588-112">Requirements</span></span>

<span data-ttu-id="94588-113">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="94588-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="94588-114">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="94588-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="94588-115">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="94588-115">**.NET Framework versions:** Available since 2.0.</span></span>
