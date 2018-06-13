---
title: 类型参数不能用作限定符
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 563010efc4f3049d330ee2b38b7f59e23292e630
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595130"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="1892b-102">类型参数不能用作限定符</span><span class="sxs-lookup"><span data-stu-id="1892b-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="1892b-103">编程元素限定包括类型参数的限定字符串中。</span><span class="sxs-lookup"><span data-stu-id="1892b-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="1892b-104">类型参数各代表构造泛型类型时，将提供的类型的必要条件。</span><span class="sxs-lookup"><span data-stu-id="1892b-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="1892b-105">它不表示特定的已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="1892b-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="1892b-106">限定字符串必须包含在编译时定义的元素。</span><span class="sxs-lookup"><span data-stu-id="1892b-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="1892b-107">以下语句可能会生成此错误。</span><span class="sxs-lookup"><span data-stu-id="1892b-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="1892b-108">**错误 ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="1892b-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1892b-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1892b-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="1892b-110">从限定字符串中，删除类型参数或将其替换为已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="1892b-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="1892b-111">如果你需要使用的构造的类型来查找正在限定的编程元素，则必须使用其他程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="1892b-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1892b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1892b-112">See Also</span></span>  
 [<span data-ttu-id="1892b-113">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="1892b-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="1892b-114">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="1892b-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="1892b-115">类型列表</span><span class="sxs-lookup"><span data-stu-id="1892b-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
