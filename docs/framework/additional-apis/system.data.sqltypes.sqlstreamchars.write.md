---
title: SqlStreamChars.Write (Char []，Int32，Int32) 方法 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e8c8ee7ab7a744c1a1d18212f1c7f9788c91ea0d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152570"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="c99cc-102">SqlStreamChars.Write (Char []，Int32，Int32) 方法</span><span class="sxs-lookup"><span data-stu-id="c99cc-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="c99cc-103">当在派生类中重写的字符序列写入当前流并将此流中的当前位置提升写入的字符数。</span><span class="sxs-lookup"><span data-stu-id="c99cc-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="c99cc-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="c99cc-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="c99cc-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="c99cc-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="c99cc-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="c99cc-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="c99cc-107">参数</span><span class="sxs-lookup"><span data-stu-id="c99cc-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="c99cc-108">要写入的字符数组。</span><span class="sxs-lookup"><span data-stu-id="c99cc-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="c99cc-109">相对于源偏移量。</span><span class="sxs-lookup"><span data-stu-id="c99cc-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="c99cc-110">要写入当前流的字符数。</span><span class="sxs-lookup"><span data-stu-id="c99cc-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="c99cc-111">备注</span><span class="sxs-lookup"><span data-stu-id="c99cc-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c99cc-112">`SqlStreamChars.Write`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="c99cc-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c99cc-113">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="c99cc-113">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c99cc-114">要求</span><span class="sxs-lookup"><span data-stu-id="c99cc-114">Requirements</span></span>

<span data-ttu-id="c99cc-115">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="c99cc-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="c99cc-116">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="c99cc-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="c99cc-117">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="c99cc-117">**.NET Framework versions:** Available since 2.0.</span></span>