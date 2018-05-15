---
title: '&#39;&lt;membername&gt; &#39;不能公开类型&#39; &lt;typename&gt; &#39;通过在项目外部&lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 36add48ebee2d1804921eeeec0b59cdd4cbafecc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="b28d9-102">&#39;&lt;membername&gt; &#39;不能公开类型&#39; &lt;typename&gt; &#39;通过在项目外部&lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="b28d9-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="b28d9-103">变量、 过程参数或函数返回暴露于其容器之外，但它被声明为必须不公开容器之外的类型。</span><span class="sxs-lookup"><span data-stu-id="b28d9-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="b28d9-104">下面的主干代码演示生成此错误的情况。</span><span class="sxs-lookup"><span data-stu-id="b28d9-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="b28d9-105">声明的类型`Protected`， `Friend`， `Protected Friend`，或`Private`旨在其声明上下文外的访问受到限制。</span><span class="sxs-lookup"><span data-stu-id="b28d9-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="b28d9-106">使用的数据，将无法具有受限制更少访问的变量的类型实现此目的。</span><span class="sxs-lookup"><span data-stu-id="b28d9-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="b28d9-107">在上面的主干代码`exposedVar`是`Public`和将公开`privateClass`到不应有权访问它的代码。</span><span class="sxs-lookup"><span data-stu-id="b28d9-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="b28d9-108">**错误 ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="b28d9-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b28d9-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b28d9-109">To correct this error</span></span>  
  
-   <span data-ttu-id="b28d9-110">变量、 过程参数或函数的访问级别的更改返回让至少为其数据类型的访问级别限制性最高。</span><span class="sxs-lookup"><span data-stu-id="b28d9-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28d9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b28d9-111">See Also</span></span>  
 [<span data-ttu-id="b28d9-112">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="b28d9-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
