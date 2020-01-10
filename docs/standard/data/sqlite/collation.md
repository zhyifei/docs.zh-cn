---
title: Collation
ms.date: 12/13/2019
description: 了解如何创建自定义排序序列。
ms.openlocfilehash: 9cc574a75c8f5347dd9bb44e36af72e50afa57b4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777391"
---
# <a name="collation"></a><span data-ttu-id="a0452-103">Collation</span><span class="sxs-lookup"><span data-stu-id="a0452-103">Collation</span></span>

<span data-ttu-id="a0452-104">比较文本值以确定顺序和相等性时，SQLite 使用排序序列。</span><span class="sxs-lookup"><span data-stu-id="a0452-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="a0452-105">在 SQL 查询中创建列或每个操作时，可以指定要使用的排序规则。</span><span class="sxs-lookup"><span data-stu-id="a0452-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="a0452-106">SQLite 默认情况下包含三个排序序列。</span><span class="sxs-lookup"><span data-stu-id="a0452-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="a0452-107">Collation</span><span class="sxs-lookup"><span data-stu-id="a0452-107">Collation</span></span> | <span data-ttu-id="a0452-108">描述</span><span class="sxs-lookup"><span data-stu-id="a0452-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="a0452-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="a0452-109">RTRIM</span></span>     | <span data-ttu-id="a0452-110">忽略尾随空格</span><span class="sxs-lookup"><span data-stu-id="a0452-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="a0452-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="a0452-111">NOCASE</span></span>    | <span data-ttu-id="a0452-112">ASCII 字符 a-z 的不区分大小写</span><span class="sxs-lookup"><span data-stu-id="a0452-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="a0452-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="a0452-113">BINARY</span></span>    | <span data-ttu-id="a0452-114">区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a0452-114">Case-sensitive.</span></span> <span data-ttu-id="a0452-115">直接比较字节</span><span class="sxs-lookup"><span data-stu-id="a0452-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="a0452-116">自定义排序规则</span><span class="sxs-lookup"><span data-stu-id="a0452-116">Custom collation</span></span>

<span data-ttu-id="a0452-117">您还可以定义自己的排序规则或使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>覆盖内置的排序规则。</span><span class="sxs-lookup"><span data-stu-id="a0452-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="a0452-118">下面的示例演示如何重写 NOCASE 排序规则以支持 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="a0452-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="a0452-119">GitHub 上提供了[完整的示例代码](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs)。</span><span class="sxs-lookup"><span data-stu-id="a0452-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="a0452-120">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="a0452-120">Like operator</span></span>

<span data-ttu-id="a0452-121">SQLite 中的 LIKE 运算符不服从排序规则。</span><span class="sxs-lookup"><span data-stu-id="a0452-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="a0452-122">默认实现的语义与 NOCASE 排序规则的语义相同。</span><span class="sxs-lookup"><span data-stu-id="a0452-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="a0452-123">对于 ASCII 字符 A 到 Z，只区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a0452-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="a0452-124">您可以使用以下杂注语句轻松地使 LIKE 运算符区分大小写：</span><span class="sxs-lookup"><span data-stu-id="a0452-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 0
```

<span data-ttu-id="a0452-125">有关重写 LIKE 运算符的实现的详细信息，请参阅[用户定义函数](user-defined-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="a0452-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0452-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0452-126">See also</span></span>

* [<span data-ttu-id="a0452-127">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="a0452-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="a0452-128">SQL 语法</span><span class="sxs-lookup"><span data-stu-id="a0452-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
