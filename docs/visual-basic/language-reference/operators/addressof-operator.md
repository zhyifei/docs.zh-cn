---
title: AddressOf 运算符
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: e88520bd7e731a35b98c1d40c5210dc5d1314911
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350272"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="8f75e-102">AddressOf 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f75e-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="8f75e-103">创建引用特定过程的委托实例。</span><span class="sxs-lookup"><span data-stu-id="8f75e-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f75e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f75e-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="8f75e-105">部件</span><span class="sxs-lookup"><span data-stu-id="8f75e-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="8f75e-106">必需。</span><span class="sxs-lookup"><span data-stu-id="8f75e-106">Required.</span></span> <span data-ttu-id="8f75e-107">指定新创建的委托所引用的过程。</span><span class="sxs-lookup"><span data-stu-id="8f75e-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f75e-108">备注</span><span class="sxs-lookup"><span data-stu-id="8f75e-108">Remarks</span></span>  
 <span data-ttu-id="8f75e-109">`AddressOf` 运算符创建指向 `procedurename`指定的 sub 或函数的委托。</span><span class="sxs-lookup"><span data-stu-id="8f75e-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="8f75e-110">如果指定的过程是实例方法，则委托同时引用实例和方法。</span><span class="sxs-lookup"><span data-stu-id="8f75e-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="8f75e-111">然后，在调用委托时，将调用指定实例的指定方法。</span><span class="sxs-lookup"><span data-stu-id="8f75e-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="8f75e-112">`AddressOf` 运算符可用作委托构造函数的操作数，或可用于可由编译器确定委托类型的上下文中使用。</span><span class="sxs-lookup"><span data-stu-id="8f75e-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f75e-113">示例</span><span class="sxs-lookup"><span data-stu-id="8f75e-113">Example</span></span>  
 <span data-ttu-id="8f75e-114">此示例使用 `AddressOf` 运算符来指定用于处理按钮的 `Click` 事件的委托。</span><span class="sxs-lookup"><span data-stu-id="8f75e-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="8f75e-115">示例</span><span class="sxs-lookup"><span data-stu-id="8f75e-115">Example</span></span>  
 <span data-ttu-id="8f75e-116">下面的示例使用 `AddressOf` 运算符来指定线程的启动函数。</span><span class="sxs-lookup"><span data-stu-id="8f75e-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="8f75e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f75e-117">See also</span></span>

- [<span data-ttu-id="8f75e-118">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="8f75e-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="8f75e-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="8f75e-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="8f75e-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="8f75e-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="8f75e-121">委托</span><span class="sxs-lookup"><span data-stu-id="8f75e-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
