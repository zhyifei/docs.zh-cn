---
title: Call 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: a04ebddc7db176188876da1082e1e6946e1e8eec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005165"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="09028-102">Call 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09028-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="09028-103">将控制转移到 `Function`、`Sub`或动态链接库（DLL）过程。</span><span class="sxs-lookup"><span data-stu-id="09028-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09028-104">语法</span><span class="sxs-lookup"><span data-stu-id="09028-104">Syntax</span></span>  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="09028-105">部件</span><span class="sxs-lookup"><span data-stu-id="09028-105">Parts</span></span>  

|||
|---|---|
|`procedureName`|<span data-ttu-id="09028-106">必需。</span><span class="sxs-lookup"><span data-stu-id="09028-106">Required.</span></span> <span data-ttu-id="09028-107">要调用的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="09028-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="09028-108">可选。</span><span class="sxs-lookup"><span data-stu-id="09028-108">Optional.</span></span> <span data-ttu-id="09028-109">表示在调用过程时传递给过程的参数的变量或表达式列表。</span><span class="sxs-lookup"><span data-stu-id="09028-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="09028-110">多个参数之间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="09028-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="09028-111">如果包括 `argumentList`，则必须将其括在括号中。</span><span class="sxs-lookup"><span data-stu-id="09028-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="09028-112">备注</span><span class="sxs-lookup"><span data-stu-id="09028-112">Remarks</span></span>

 <span data-ttu-id="09028-113">在调用过程时，可以使用 `Call` 关键字。</span><span class="sxs-lookup"><span data-stu-id="09028-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="09028-114">对于大多数过程调用，不需要使用此关键字。</span><span class="sxs-lookup"><span data-stu-id="09028-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="09028-115">当被调用的表达式不是以标识符开头时，通常使用 `Call` 关键字。</span><span class="sxs-lookup"><span data-stu-id="09028-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="09028-116">不建议将 `Call` 关键字用于其他用途。</span><span class="sxs-lookup"><span data-stu-id="09028-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="09028-117">如果过程返回值，则 `Call` 语句将其丢弃。</span><span class="sxs-lookup"><span data-stu-id="09028-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="09028-118">示例</span><span class="sxs-lookup"><span data-stu-id="09028-118">Example</span></span>

 <span data-ttu-id="09028-119">下面的代码演示了两个示例，其中 `Call` 关键字是调用过程所必需的。</span><span class="sxs-lookup"><span data-stu-id="09028-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="09028-120">在这两个示例中，调用的表达式不以标识符开头。</span><span class="sxs-lookup"><span data-stu-id="09028-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="09028-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09028-121">See also</span></span>

- [<span data-ttu-id="09028-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="09028-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="09028-123">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="09028-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="09028-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="09028-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="09028-125">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="09028-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
