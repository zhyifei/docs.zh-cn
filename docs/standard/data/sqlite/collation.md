---
title: 排序规则
ms.date: 12/13/2019
description: 了解如何创建自定义排序序列。
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242967"
---
# <a name="collation"></a><span data-ttu-id="fc2a2-103">排序规则</span><span class="sxs-lookup"><span data-stu-id="fc2a2-103">Collation</span></span>

<span data-ttu-id="fc2a2-104">SQLite 在比较 TEXT 值时使用排序序列确定顺序和相等性。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="fc2a2-105">可以指定在 SQL 查询中创建列时或是对每个操作要使用的排序规则。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="fc2a2-106">SQLite 在默认情况下包含三种排序序列。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="fc2a2-107">排序规则</span><span class="sxs-lookup"><span data-stu-id="fc2a2-107">Collation</span></span> | <span data-ttu-id="fc2a2-108">描述</span><span class="sxs-lookup"><span data-stu-id="fc2a2-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="fc2a2-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="fc2a2-109">RTRIM</span></span>     | <span data-ttu-id="fc2a2-110">忽略尾随空格</span><span class="sxs-lookup"><span data-stu-id="fc2a2-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="fc2a2-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="fc2a2-111">NOCASE</span></span>    | <span data-ttu-id="fc2a2-112">对于 ASCII 字符 A-Z 不区分大小写</span><span class="sxs-lookup"><span data-stu-id="fc2a2-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="fc2a2-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="fc2a2-113">BINARY</span></span>    | <span data-ttu-id="fc2a2-114">区分大小写。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-114">Case-sensitive.</span></span> <span data-ttu-id="fc2a2-115">直接比较字节</span><span class="sxs-lookup"><span data-stu-id="fc2a2-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="fc2a2-116">自定义排序规则</span><span class="sxs-lookup"><span data-stu-id="fc2a2-116">Custom collation</span></span>

<span data-ttu-id="fc2a2-117">还可以使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A> 定义自己的排序序列或替代内置排序序列。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="fc2a2-118">下面的示例演示如何替代 NOCASE 排序规则以支持 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="fc2a2-119">GitHub 上提供了[完整示例代码](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs)。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-119">The [full sample code](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="fc2a2-120">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="fc2a2-120">Like operator</span></span>

<span data-ttu-id="fc2a2-121">SQLite 中的 LIKE 运算符不遵循排序规则。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="fc2a2-122">默认实现的语义与 NOCASE 排序规则相同。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="fc2a2-123">只对 ASCII 字符 A 到 Z 不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="fc2a2-124">可以使用以下 pragma 语句轻松地使 LIKE 运算符区分大小写：</span><span class="sxs-lookup"><span data-stu-id="fc2a2-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="fc2a2-125">有关替代 LIKE 运算符的实现的详细信息，请参阅[用户定义的函数](user-defined-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="fc2a2-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc2a2-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc2a2-126">See also</span></span>

* [<span data-ttu-id="fc2a2-127">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="fc2a2-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="fc2a2-128">SQL 语法</span><span class="sxs-lookup"><span data-stu-id="fc2a2-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
