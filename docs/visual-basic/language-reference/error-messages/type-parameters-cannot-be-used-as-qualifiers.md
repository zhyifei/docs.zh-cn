---
title: 类型参数不能用作限定符
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: ba7348ae50965ffcf2719b20934451916c8fa95a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296350"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="cda1c-102">类型参数不能用作限定符</span><span class="sxs-lookup"><span data-stu-id="cda1c-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="cda1c-103">编程元素限定包含类型参数的限定字符串中。</span><span class="sxs-lookup"><span data-stu-id="cda1c-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="cda1c-104">类型参数表示构造泛型类型时将提供的类型的要求。</span><span class="sxs-lookup"><span data-stu-id="cda1c-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="cda1c-105">它不表示特定的已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="cda1c-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="cda1c-106">限定字符串必须包含在编译时定义的元素。</span><span class="sxs-lookup"><span data-stu-id="cda1c-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="cda1c-107">以下语句可能会生成此错误。</span><span class="sxs-lookup"><span data-stu-id="cda1c-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="cda1c-108">**错误 ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="cda1c-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cda1c-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="cda1c-109">To correct this error</span></span>  
  
1. <span data-ttu-id="cda1c-110">从限定字符串中删除类型参数或替换已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="cda1c-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="cda1c-111">如果您需要使用一个构造的类型来查找正在限定的编程元素，则必须使用其他程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="cda1c-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda1c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cda1c-112">See also</span></span>

- [<span data-ttu-id="cda1c-113">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="cda1c-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="cda1c-114">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="cda1c-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="cda1c-115">Type List</span><span class="sxs-lookup"><span data-stu-id="cda1c-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
