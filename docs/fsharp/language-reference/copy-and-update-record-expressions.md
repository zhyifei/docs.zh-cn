---
title: '复制和更新记录的表达式 （F #）'
description: 了解如何编写的复制和更新记录表达式复制现有的记录，更新指定的字段，并返回已更新的记录。
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 000746b6e76349ae6d8f338519a58034f4e29020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563054"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="ca262-103">复制和更新记录表达式</span><span class="sxs-lookup"><span data-stu-id="ca262-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="ca262-104">A*复制和更新记录表达式*是复制现有记录，更新指定的字段，并返回已更新的记录的表达式。</span><span class="sxs-lookup"><span data-stu-id="ca262-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="ca262-105">语法</span><span class="sxs-lookup"><span data-stu-id="ca262-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="ca262-106">备注</span><span class="sxs-lookup"><span data-stu-id="ca262-106">Remarks</span></span>
<span data-ttu-id="ca262-107">记录是默认情况下，不可变的因此可能是不会更新到现有记录。</span><span class="sxs-lookup"><span data-stu-id="ca262-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="ca262-108">若要创建的记录的所有字段的更新的记录将不得不再次指定。</span><span class="sxs-lookup"><span data-stu-id="ca262-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="ca262-109">为了简化此任务*复制和更新记录表达式*可用。</span><span class="sxs-lookup"><span data-stu-id="ca262-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="ca262-110">此表达式采用现有记录，以通过使用表达式中的指定的字段和缺少的字段指定的表达式创建一个新的相同的类型。</span><span class="sxs-lookup"><span data-stu-id="ca262-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="ca262-111">当你需要复制现有记录，并可能会更改某些字段值时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="ca262-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="ca262-112">以为例新创建的记录。</span><span class="sxs-lookup"><span data-stu-id="ca262-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="ca262-113">如果要仅在你可以使用该记录的字段上更新*复制和更新记录表达式*类似于以下：</span><span class="sxs-lookup"><span data-stu-id="ca262-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="ca262-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca262-114">See Also</span></span>
[<span data-ttu-id="ca262-115">记录</span><span class="sxs-lookup"><span data-stu-id="ca262-115">Records</span></span>](records.md)

[<span data-ttu-id="ca262-116">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="ca262-116">F# Language Reference</span></span>](index.md)
