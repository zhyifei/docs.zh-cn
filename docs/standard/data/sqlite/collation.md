---
title: 排序规则
ms.date: 12/13/2019
description: 了解如何创建自定义整理序列。
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242967"
---
# <a name="collation"></a><span data-ttu-id="38487-103">排序规则</span><span class="sxs-lookup"><span data-stu-id="38487-103">Collation</span></span>

<span data-ttu-id="38487-104">SQLite 在比较 TEXT 值以确定顺序和相等性时使用分字序列。</span><span class="sxs-lookup"><span data-stu-id="38487-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="38487-105">您可以指定在 SQL 查询中创建列或每个操作时要使用的排序规则。</span><span class="sxs-lookup"><span data-stu-id="38487-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="38487-106">默认情况下，SQLite 包括三个整理序列。</span><span class="sxs-lookup"><span data-stu-id="38487-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="38487-107">排序规则</span><span class="sxs-lookup"><span data-stu-id="38487-107">Collation</span></span> | <span data-ttu-id="38487-108">说明</span><span class="sxs-lookup"><span data-stu-id="38487-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="38487-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="38487-109">RTRIM</span></span>     | <span data-ttu-id="38487-110">忽略尾随空格</span><span class="sxs-lookup"><span data-stu-id="38487-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="38487-111">无案例</span><span class="sxs-lookup"><span data-stu-id="38487-111">NOCASE</span></span>    | <span data-ttu-id="38487-112">ASCII 字符 A-Z 不区分大小写</span><span class="sxs-lookup"><span data-stu-id="38487-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="38487-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="38487-113">BINARY</span></span>    | <span data-ttu-id="38487-114">区分大小写。</span><span class="sxs-lookup"><span data-stu-id="38487-114">Case-sensitive.</span></span> <span data-ttu-id="38487-115">直接比较字节</span><span class="sxs-lookup"><span data-stu-id="38487-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="38487-116">自定义排序规则</span><span class="sxs-lookup"><span data-stu-id="38487-116">Custom collation</span></span>

<span data-ttu-id="38487-117">您还可以定义自己的整理序列或使用 重写的序列<xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>。</span><span class="sxs-lookup"><span data-stu-id="38487-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="38487-118">下面的示例显示覆盖 NOCASE 排序规则以支持 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="38487-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="38487-119">[完整的示例代码](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs)在 GitHub 上可用。</span><span class="sxs-lookup"><span data-stu-id="38487-119">The [full sample code](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="38487-120">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="38487-120">Like operator</span></span>

<span data-ttu-id="38487-121">SQLite 中的 LIKE 运算符不遵循排序规则。</span><span class="sxs-lookup"><span data-stu-id="38487-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="38487-122">默认实现具有与 NOCASE 排序规则相同的语义。</span><span class="sxs-lookup"><span data-stu-id="38487-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="38487-123">它仅对 ASCII 字符 A 到 Z 不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="38487-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="38487-124">通过使用以下杂注语句，可以轻松地使 LIKE 运算符区分大小写：</span><span class="sxs-lookup"><span data-stu-id="38487-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="38487-125">有关重写 LIKE 运算符实现的详细信息，请参阅[用户定义的函数](user-defined-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="38487-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="38487-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38487-126">See also</span></span>

* [<span data-ttu-id="38487-127">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="38487-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="38487-128">SQL 语法</span><span class="sxs-lookup"><span data-stu-id="38487-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
