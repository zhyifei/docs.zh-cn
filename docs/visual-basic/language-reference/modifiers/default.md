---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: 555e15110c7af501de05d1f395a72ca4b7800054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595131"
---
# <a name="default-visual-basic"></a><span data-ttu-id="2d216-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d216-102">Default (Visual Basic)</span></span>
<span data-ttu-id="2d216-103">标识为其类、 结构或接口的默认属性的属性。</span><span class="sxs-lookup"><span data-stu-id="2d216-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d216-104">备注</span><span class="sxs-lookup"><span data-stu-id="2d216-104">Remarks</span></span>  
 <span data-ttu-id="2d216-105">类、 结构或接口可以指定最多为其属性之一*默认属性*，前提是属性采用至少一个参数。</span><span class="sxs-lookup"><span data-stu-id="2d216-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="2d216-106">如果代码使得对类或结构的引用，而不必指定的成员，Visual Basic 将解析的默认属性该引用。</span><span class="sxs-lookup"><span data-stu-id="2d216-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="2d216-107">默认属性可能会导致小减少源代码的字符，但它们会导致代码更难阅读。</span><span class="sxs-lookup"><span data-stu-id="2d216-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="2d216-108">如果在发出对类或结构名称的引用时，调用代码不熟悉类或结构，它无法确定该引用访问的类或结构本身或默认属性。</span><span class="sxs-lookup"><span data-stu-id="2d216-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="2d216-109">这可能导致编译器错误或细微的运行时逻辑错误。</span><span class="sxs-lookup"><span data-stu-id="2d216-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="2d216-110">你可以始终使用某种程度上减少默认属性的几率[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)设置编译器类型检查到`On`。</span><span class="sxs-lookup"><span data-stu-id="2d216-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="2d216-111">如果你计划可以使用预定义的类或结构中你的代码，必须确定它是否具有默认属性，以及如果是这样，其名称是什么。</span><span class="sxs-lookup"><span data-stu-id="2d216-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="2d216-112">由于这些缺点，应考虑未定义默认属性。</span><span class="sxs-lookup"><span data-stu-id="2d216-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="2d216-113">为了代码的可读性，你应还考虑始终显式引用所有属性，包括默认属性。</span><span class="sxs-lookup"><span data-stu-id="2d216-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="2d216-114">`Default`修饰符可用于在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="2d216-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="2d216-115">Property 语句</span><span class="sxs-lookup"><span data-stu-id="2d216-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d216-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d216-116">See Also</span></span>  
 [<span data-ttu-id="2d216-117">如何： 声明和 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="2d216-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="2d216-118">关键字</span><span class="sxs-lookup"><span data-stu-id="2d216-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
