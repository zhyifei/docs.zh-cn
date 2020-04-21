---
title: 复制和更新记录表达式
description: 了解如何编写复制现有记录或匿名记录、更新指定字段以及返回更新的记录或匿名记录的"复制和更新表达式"。
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739278"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="ce2e3-103">复制和更新记录表达式</span><span class="sxs-lookup"><span data-stu-id="ce2e3-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="ce2e3-104">*复制和更新记录表达式*是复制现有记录、更新指定字段并返回更新的记录的表达式。</span><span class="sxs-lookup"><span data-stu-id="ce2e3-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce2e3-105">语法</span><span class="sxs-lookup"><span data-stu-id="ce2e3-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="ce2e3-106">备注</span><span class="sxs-lookup"><span data-stu-id="ce2e3-106">Remarks</span></span>

<span data-ttu-id="ce2e3-107">默认情况下，记录和匿名记录是不可变的，因此无法更新现有记录。</span><span class="sxs-lookup"><span data-stu-id="ce2e3-107">Records and anonymous records are immutable by default, so it is not possible to update an existing record.</span></span> <span data-ttu-id="ce2e3-108">要创建更新的记录，必须再次指定记录的所有字段。</span><span class="sxs-lookup"><span data-stu-id="ce2e3-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="ce2e3-109">为了简化此任务，可以使用*复制和更新表达式*。</span><span class="sxs-lookup"><span data-stu-id="ce2e3-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="ce2e3-110">此表达式采用现有记录，使用表达式中的指定字段和表达式指定的缺失字段创建新的相同类型。</span><span class="sxs-lookup"><span data-stu-id="ce2e3-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="ce2e3-111">当您必须复制现有记录并可能更改某些字段值时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="ce2e3-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="ce2e3-112">例如，以新创建的记录为例。</span><span class="sxs-lookup"><span data-stu-id="ce2e3-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="ce2e3-113">要仅更新该记录中的两个字段，可以使用*复制和更新记录表达式*：</span><span class="sxs-lookup"><span data-stu-id="ce2e3-113">To update only two fields in that record you can use the *copy and update record expression*:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="ce2e3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce2e3-114">See also</span></span>

- [<span data-ttu-id="ce2e3-115">记录</span><span class="sxs-lookup"><span data-stu-id="ce2e3-115">Records</span></span>](records.md)
- [<span data-ttu-id="ce2e3-116">匿名记录</span><span class="sxs-lookup"><span data-stu-id="ce2e3-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="ce2e3-117">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="ce2e3-117">F# Language Reference</span></span>](index.md)
