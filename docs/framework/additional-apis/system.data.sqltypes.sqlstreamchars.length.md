---
title: SqlStreamChars.Length 属性 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 1ee15641e697a9d5d146f921640c73ff84a5c335
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152710"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="71cd9-102">SqlStreamChars.Length 属性</span><span class="sxs-lookup"><span data-stu-id="71cd9-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="71cd9-103">当在派生类中重写时获取当前流的长度。</span><span class="sxs-lookup"><span data-stu-id="71cd9-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="71cd9-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="71cd9-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="71cd9-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="71cd9-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="71cd9-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="71cd9-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="71cd9-107">语法</span><span class="sxs-lookup"><span data-stu-id="71cd9-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="71cd9-108">属性值</span><span class="sxs-lookup"><span data-stu-id="71cd9-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="71cd9-109">流的长度。</span><span class="sxs-lookup"><span data-stu-id="71cd9-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="71cd9-110">备注</span><span class="sxs-lookup"><span data-stu-id="71cd9-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="71cd9-111">`SqlStreamChars.Length`属性是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="71cd9-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="71cd9-112">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="71cd9-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="71cd9-113">要求</span><span class="sxs-lookup"><span data-stu-id="71cd9-113">Requirements</span></span>

<span data-ttu-id="71cd9-114">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="71cd9-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="71cd9-115">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="71cd9-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="71cd9-116">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="71cd9-116">**.NET Framework versions:** Available since 2.0.</span></span>