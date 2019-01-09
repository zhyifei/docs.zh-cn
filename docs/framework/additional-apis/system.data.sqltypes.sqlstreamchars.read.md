---
title: SqlStreamChars.Read (Char []，Int32，Int32) 方法 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 87bff6dd78743ae08a5a3db8a783b56a0b7c3f24
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152530"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="6b636-102">SqlStreamChars.Read (Char []，Int32，Int32) 方法</span><span class="sxs-lookup"><span data-stu-id="6b636-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="6b636-103">当在派生类中重写，请从输入流读取下一组字符。</span><span class="sxs-lookup"><span data-stu-id="6b636-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="6b636-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="6b636-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="6b636-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="6b636-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="6b636-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="6b636-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="6b636-107">参数</span><span class="sxs-lookup"><span data-stu-id="6b636-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="6b636-108">要读取的字符数组。</span><span class="sxs-lookup"><span data-stu-id="6b636-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="6b636-109">相对于源偏移量。</span><span class="sxs-lookup"><span data-stu-id="6b636-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="6b636-110">要从当前流中读取的字符数。</span><span class="sxs-lookup"><span data-stu-id="6b636-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="6b636-111">返回</span><span class="sxs-lookup"><span data-stu-id="6b636-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="6b636-112">读入缓冲区的总字符数。</span><span class="sxs-lookup"><span data-stu-id="6b636-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b636-113">备注</span><span class="sxs-lookup"><span data-stu-id="6b636-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="6b636-114">`SqlStreamChars.Read`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="6b636-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6b636-115">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="6b636-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b636-116">要求</span><span class="sxs-lookup"><span data-stu-id="6b636-116">Requirements</span></span>

<span data-ttu-id="6b636-117">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="6b636-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="6b636-118">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="6b636-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="6b636-119">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="6b636-119">**.NET Framework versions:** Available since 2.0.</span></span>