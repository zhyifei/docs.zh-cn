---
title: "类型参数不能用作限定符"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords: BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58be51e0c05750ee044f0287cde8db037718b4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="9ef36-102">类型参数不能用作限定符</span><span class="sxs-lookup"><span data-stu-id="9ef36-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="9ef36-103">编程元素限定包括类型参数的限定字符串中。</span><span class="sxs-lookup"><span data-stu-id="9ef36-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="9ef36-104">类型参数各代表构造泛型类型时，将提供的类型的必要条件。</span><span class="sxs-lookup"><span data-stu-id="9ef36-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="9ef36-105">它不表示特定的已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="9ef36-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="9ef36-106">限定字符串必须包含在编译时定义的元素。</span><span class="sxs-lookup"><span data-stu-id="9ef36-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="9ef36-107">以下语句可能会生成此错误。</span><span class="sxs-lookup"><span data-stu-id="9ef36-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="9ef36-108">**错误 ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="9ef36-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ef36-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9ef36-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="9ef36-110">从限定字符串中，删除类型参数或将其替换为已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="9ef36-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="9ef36-111">如果你需要使用的构造的类型来查找正在限定的编程元素，则必须使用其他程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="9ef36-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef36-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef36-112">See Also</span></span>  
 [<span data-ttu-id="9ef36-113">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="9ef36-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="9ef36-114">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="9ef36-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="9ef36-115">类型列表</span><span class="sxs-lookup"><span data-stu-id="9ef36-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
