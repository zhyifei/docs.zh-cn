---
title: “<membername>”不能通过 <typename>“<containertype>”在项目外部公开类型“<containertypename>”
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 16f579a05236ba8977a071cb08068be8e98799f8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818329"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="e1094-102">'\<成员名称 > 不能公开类型\<类型名称 > 通过在项目外部\<containertype >'\<containertypename ></span><span class="sxs-lookup"><span data-stu-id="e1094-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="e1094-103">变量、 过程参数或函数返回公开其容器外，但它被声明为不必须在容器外公开的类型。</span><span class="sxs-lookup"><span data-stu-id="e1094-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="e1094-104">下面的主干代码显示了将生成此错误的情况。</span><span class="sxs-lookup"><span data-stu-id="e1094-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="e1094-105">声明的类型`Protected`， `Friend`， `Protected Friend`，或`Private`用于其声明上下文以外的访问受到限制。</span><span class="sxs-lookup"><span data-stu-id="e1094-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="e1094-106">使用与数据，将无法具有受限制更少访问的变量的类型实现此目的。</span><span class="sxs-lookup"><span data-stu-id="e1094-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="e1094-107">在上面的主干代码`exposedVar`是`Public`，并将公开`privateClass`不应有权访问它的代码。</span><span class="sxs-lookup"><span data-stu-id="e1094-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="e1094-108">**错误 ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="e1094-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e1094-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e1094-109">To correct this error</span></span>  
  
-   <span data-ttu-id="e1094-110">更改访问级别，变量、 过程参数或函数的返回让至少作为其数据类型的访问级别限制性最高。</span><span class="sxs-lookup"><span data-stu-id="e1094-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1094-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1094-111">See also</span></span>

- [<span data-ttu-id="e1094-112">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="e1094-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
