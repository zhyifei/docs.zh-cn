---
title: 复制和更新记录表达式
description: 了解如何编写一个 "复制和更新表达式", 该表达式复制现有记录或匿名记录, 更新指定字段, 并返回已更新的记录或匿名记录。
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630376"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="828b0-103">复制和更新记录表达式</span><span class="sxs-lookup"><span data-stu-id="828b0-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="828b0-104">*复制和更新记录表达式*是一个表达式, 该表达式复制现有记录、更新指定字段并返回已更新的记录。</span><span class="sxs-lookup"><span data-stu-id="828b0-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="828b0-105">语法</span><span class="sxs-lookup"><span data-stu-id="828b0-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="828b0-106">备注</span><span class="sxs-lookup"><span data-stu-id="828b0-106">Remarks</span></span>

<span data-ttu-id="828b0-107">记录和匿名记录在默认情况下是不可变的, 因此不能更新现有记录。</span><span class="sxs-lookup"><span data-stu-id="828b0-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="828b0-108">若要创建更新的记录, 则必须重新指定记录的所有字段。</span><span class="sxs-lookup"><span data-stu-id="828b0-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="828b0-109">若要简化此任务, 可以使用*复制和更新表达式*。</span><span class="sxs-lookup"><span data-stu-id="828b0-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="828b0-110">此表达式使用现有记录, 通过使用表达式中指定的字段和表达式指定的缺失字段来创建同一类型的新记录。</span><span class="sxs-lookup"><span data-stu-id="828b0-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="828b0-111">当必须复制现有记录, 并且可能更改某些字段值时, 这会很有用。</span><span class="sxs-lookup"><span data-stu-id="828b0-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="828b0-112">用于实例创建新的记录。</span><span class="sxs-lookup"><span data-stu-id="828b0-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="828b0-113">如果仅更新该记录的字段, 可以使用如下所示的*复制和更新记录表达式*:</span><span class="sxs-lookup"><span data-stu-id="828b0-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="828b0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="828b0-114">See also</span></span>

- [<span data-ttu-id="828b0-115">记录</span><span class="sxs-lookup"><span data-stu-id="828b0-115">Records</span></span>](records.md)
- [<span data-ttu-id="828b0-116">匿名记录</span><span class="sxs-lookup"><span data-stu-id="828b0-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="828b0-117">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="828b0-117">F# Language Reference</span></span>](index.md)
