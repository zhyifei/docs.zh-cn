---
title: AddressOf 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 098ca95687d8b0e9f4ac90d5c7e0df9a9a0ad950
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760372"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="633f4-102">AddressOf 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="633f4-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="633f4-103">创建一个委托实例来引用特定过程。</span><span class="sxs-lookup"><span data-stu-id="633f4-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="633f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="633f4-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="633f4-105">部件</span><span class="sxs-lookup"><span data-stu-id="633f4-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="633f4-106">必需。</span><span class="sxs-lookup"><span data-stu-id="633f4-106">Required.</span></span> <span data-ttu-id="633f4-107">指定引用的新创建的委托的过程。</span><span class="sxs-lookup"><span data-stu-id="633f4-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="633f4-108">备注</span><span class="sxs-lookup"><span data-stu-id="633f4-108">Remarks</span></span>  
 <span data-ttu-id="633f4-109">`AddressOf`运算符创建一个委托，它指向 sub 或通过指定函数`procedurename`。</span><span class="sxs-lookup"><span data-stu-id="633f4-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="633f4-110">当指定的过程是实例方法的委托然后引用实例和方法。</span><span class="sxs-lookup"><span data-stu-id="633f4-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="633f4-111">然后，当调用委托的指定实例的指定的方法调用。</span><span class="sxs-lookup"><span data-stu-id="633f4-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="633f4-112">`AddressOf`运算符可以用作委托构造函数的操作数，或可在其中可以由编译器确定委托类型的上下文中。</span><span class="sxs-lookup"><span data-stu-id="633f4-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="633f4-113">示例</span><span class="sxs-lookup"><span data-stu-id="633f4-113">Example</span></span>  
 <span data-ttu-id="633f4-114">此示例使用`AddressOf`运算符来指定一个委托来处理`Click`按钮的事件。</span><span class="sxs-lookup"><span data-stu-id="633f4-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="633f4-115">示例</span><span class="sxs-lookup"><span data-stu-id="633f4-115">Example</span></span>  
 <span data-ttu-id="633f4-116">下面的示例使用`AddressOf`运算符来指定线程的启动函数。</span><span class="sxs-lookup"><span data-stu-id="633f4-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="633f4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="633f4-117">See also</span></span>

- [<span data-ttu-id="633f4-118">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="633f4-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="633f4-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="633f4-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="633f4-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="633f4-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="633f4-121">委托</span><span class="sxs-lookup"><span data-stu-id="633f4-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
