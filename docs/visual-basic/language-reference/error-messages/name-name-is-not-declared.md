---
title: "名称 &quot;&lt;名称&gt;未声明 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1396f24a34a37db064e73d7e259c04050f409ad2
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="b43fc-102">名称 '&lt;名称&gt;未声明</span><span class="sxs-lookup"><span data-stu-id="b43fc-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="b43fc-103">语句引用的编程元素，但编译器找不到具有该准确名称的元素。</span><span class="sxs-lookup"><span data-stu-id="b43fc-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="b43fc-104">**错误 ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="b43fc-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b43fc-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b43fc-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="b43fc-106">检查引用语句中名称的拼写。</span><span class="sxs-lookup"><span data-stu-id="b43fc-106">Check the spelling of the name in the referring statement.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b43fc-107">不区分大小写，但是拼写中的任何其他变化都会被视为完全不同的名称。</span><span class="sxs-lookup"><span data-stu-id="b43fc-107"> is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="b43fc-108">请注意，下划线 (`_`) 是名称的一部分，因此也是拼写的一部分。</span><span class="sxs-lookup"><span data-stu-id="b43fc-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="b43fc-109">检查您是否具有成员访问运算符 (`.`) 对象及其成员之间。</span><span class="sxs-lookup"><span data-stu-id="b43fc-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="b43fc-110">例如，如果您有<xref:System.Windows.Forms.TextBox>控件名为`TextBox1`，以访问其<xref:System.Windows.Forms.TextBoxBase.Text%2A>属性应键入`TextBox1.Text`。</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="b43fc-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="b43fc-111">如果你转而键入 `TextBox1Text`，则会创建不同的名称。</span><span class="sxs-lookup"><span data-stu-id="b43fc-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="b43fc-112">如果任何对象成员访问的语法正确的拼写正确，请验证已声明元素。</span><span class="sxs-lookup"><span data-stu-id="b43fc-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="b43fc-113">有关详细信息，请参阅[声明元素](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b43fc-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="b43fc-114">如果已声明的编程元素，检查它是否在范围。</span><span class="sxs-lookup"><span data-stu-id="b43fc-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="b43fc-115">如果引用的语句声明的编程元素的区域外，您可能需要限定该元素名称。</span><span class="sxs-lookup"><span data-stu-id="b43fc-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="b43fc-116">有关详细信息，请参阅[在 Visual Basic 中的作用域](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。</span><span class="sxs-lookup"><span data-stu-id="b43fc-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43fc-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b43fc-117">See Also</span></span>  
 <span data-ttu-id="b43fc-118">[声明和常量摘要](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span><span class="sxs-lookup"><span data-stu-id="b43fc-118">[Declarations and Constants Summary](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span></span>  
<span data-ttu-id="b43fc-119"> [Visual Basic 命名约定](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="b43fc-119"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="b43fc-120"> [已声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="b43fc-120"> [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="b43fc-121"> [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="b43fc-121"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
