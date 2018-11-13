---
title: 复制和更新记录表达式 （F#）
description: 了解如何编写的复制和更新记录表达式复制现有的记录，更新指定的字段，并返回已更新的记录。
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: d2b089e8a7fc5c7ee26139003e23d2eaa8a3174e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "45990838"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="2a4bb-103">复制和更新记录表达式</span><span class="sxs-lookup"><span data-stu-id="2a4bb-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="2a4bb-104">一个*复制和更新记录表达式*一个表达式，将复制的现有记录、 更新指定的字段，并返回已更新的记录。</span><span class="sxs-lookup"><span data-stu-id="2a4bb-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a4bb-105">语法</span><span class="sxs-lookup"><span data-stu-id="2a4bb-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="2a4bb-106">备注</span><span class="sxs-lookup"><span data-stu-id="2a4bb-106">Remarks</span></span>

<span data-ttu-id="2a4bb-107">记录是默认情况下，固定不变的因此可能是不会更新到现有记录。</span><span class="sxs-lookup"><span data-stu-id="2a4bb-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="2a4bb-108">若要创建已更新的记录的记录的所有字段将需要再次指定。</span><span class="sxs-lookup"><span data-stu-id="2a4bb-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="2a4bb-109">若要简化此任务*复制和更新记录表达式*可用。</span><span class="sxs-lookup"><span data-stu-id="2a4bb-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="2a4bb-110">此表达式采用现有记录，通过使用指定的表达式的字段和由表达式指定的缺失字段创建一个新的相同的类型。</span><span class="sxs-lookup"><span data-stu-id="2a4bb-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="2a4bb-111">您需要复制现有记录，并可能更改的某些字段值时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="2a4bb-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="2a4bb-112">需要对实例的新创建的记录。</span><span class="sxs-lookup"><span data-stu-id="2a4bb-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="2a4bb-113">如果您打算更新仅在您可以使用该记录的字段*复制和更新记录表达式*如下所示：</span><span class="sxs-lookup"><span data-stu-id="2a4bb-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="2a4bb-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a4bb-114">See also</span></span>

- [<span data-ttu-id="2a4bb-115">记录</span><span class="sxs-lookup"><span data-stu-id="2a4bb-115">Records</span></span>](records.md)
- [<span data-ttu-id="2a4bb-116">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="2a4bb-116">F# Language Reference</span></span>](index.md)
