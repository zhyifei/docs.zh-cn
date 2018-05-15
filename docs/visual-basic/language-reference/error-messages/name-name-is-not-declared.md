---
title: 名称&#39;&lt;名称&gt;&#39;未声明
ms.date: 07/20/2015
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: e17017e84720a2581abc5115338352aacc02d473
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="26356-102">名称&#39;&lt;名称&gt;&#39;未声明</span><span class="sxs-lookup"><span data-stu-id="26356-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="26356-103">语句引用一个编程元素，但编译器找不到具有相同名称的元素。</span><span class="sxs-lookup"><span data-stu-id="26356-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="26356-104">**错误 ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="26356-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26356-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="26356-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="26356-106">检查引用语句中名称的拼写。</span><span class="sxs-lookup"><span data-stu-id="26356-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="26356-107">Visual Basic 不区分大小写，但拼写中的任何其他变体都会被视为完全不同的名称。</span><span class="sxs-lookup"><span data-stu-id="26356-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="26356-108">请注意，下划线 (`_`) 是名称的一部分，因此也是拼写的一部分。</span><span class="sxs-lookup"><span data-stu-id="26356-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="26356-109">检查你具有成员访问运算符 (`.`) 对象和其成员之间。</span><span class="sxs-lookup"><span data-stu-id="26356-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="26356-110">例如，如果你拥有名为 <xref:System.Windows.Forms.TextBox> 的 `TextBox1`控件，则要键入 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 才可访问其 `TextBox1.Text`。</span><span class="sxs-lookup"><span data-stu-id="26356-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="26356-111">如果你转而键入 `TextBox1Text`，则会创建不同的名称。</span><span class="sxs-lookup"><span data-stu-id="26356-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="26356-112">如果拼写正确，以及任何对象成员访问的语法正确，请验证已声明元素。</span><span class="sxs-lookup"><span data-stu-id="26356-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="26356-113">有关详细信息，请参阅[声明元素](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="26356-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="26356-114">如果已声明的编程元素，请检查它是否在作用域。</span><span class="sxs-lookup"><span data-stu-id="26356-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="26356-115">如果引用语句位于声明编程元素的区域外，你可能需要限定元素名称。</span><span class="sxs-lookup"><span data-stu-id="26356-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="26356-116">有关详细信息，请参阅[在 Visual Basic 中的作用域](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。</span><span class="sxs-lookup"><span data-stu-id="26356-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26356-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="26356-117">See Also</span></span>  
 [<span data-ttu-id="26356-118">声明和常量摘要</span><span class="sxs-lookup"><span data-stu-id="26356-118">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [<span data-ttu-id="26356-119">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="26356-119">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="26356-120">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="26356-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="26356-121">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="26356-121">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
