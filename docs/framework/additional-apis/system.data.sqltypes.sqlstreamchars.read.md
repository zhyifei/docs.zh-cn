---
title: SqlStreamChars （Char []，Int32，Int32）方法（SqlTypes）
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
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395756"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="00c37-102">SqlStreamChars （Char []，Int32，Int32）方法</span><span class="sxs-lookup"><span data-stu-id="00c37-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="00c37-103">当在派生类中重写时，从输入流中读取下一组字符。</span><span class="sxs-lookup"><span data-stu-id="00c37-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="00c37-104">包含此方法的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="00c37-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="00c37-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="00c37-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="00c37-106">对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="00c37-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="00c37-107">参数</span><span class="sxs-lookup"><span data-stu-id="00c37-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="00c37-108">要读取的字符数组。</span><span class="sxs-lookup"><span data-stu-id="00c37-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="00c37-109">相对于原点的偏移量。</span><span class="sxs-lookup"><span data-stu-id="00c37-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="00c37-110">要从当前流中读取的字符数。</span><span class="sxs-lookup"><span data-stu-id="00c37-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="00c37-111">返回</span><span class="sxs-lookup"><span data-stu-id="00c37-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="00c37-112">读入缓冲区的总字符数。</span><span class="sxs-lookup"><span data-stu-id="00c37-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="00c37-113">备注</span><span class="sxs-lookup"><span data-stu-id="00c37-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="00c37-114">@No__t-0 方法是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="00c37-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="00c37-115">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="00c37-115">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="00c37-116">要求</span><span class="sxs-lookup"><span data-stu-id="00c37-116">Requirements</span></span>

<span data-ttu-id="00c37-117">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="00c37-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="00c37-118">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="00c37-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="00c37-119">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="00c37-119">**.NET Framework versions:** Available since 2.0.</span></span>
