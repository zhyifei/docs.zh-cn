---
title: "类型&lt;typename&gt;不符合 cls 的 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
dev_langs:
- VB
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
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
ms.openlocfilehash: a8d65568e862c941d5b927582833dff803219bf9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="eeead-102">类型&lt;typename&gt;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="eeead-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="eeead-103">使用不符合 CLS 的数据类型声明变量、 属性或函数返回。</span><span class="sxs-lookup"><span data-stu-id="eeead-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="eeead-104">应用程序，以符合[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，它必须只使用符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="eeead-104">For an application to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="eeead-105">以下 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 数据类型不符合 CLS：</span><span class="sxs-lookup"><span data-stu-id="eeead-105">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="eeead-106">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="eeead-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="eeead-107">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="eeead-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="eeead-108">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="eeead-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="eeead-109">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="eeead-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="eeead-110">**错误 ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="eeead-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eeead-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="eeead-111">To correct this error</span></span>  
  
-   <span data-ttu-id="eeead-112">如果您的应用程序必须是符合 cls，则更改此元素的数据类型为最接近的符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="eeead-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="eeead-113">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="eeead-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="eeead-114">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="eeead-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="eeead-115">如果您的应用程序不需要是符合 cls，则不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="eeead-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="eeead-116">应该注意它是不符合，但是。</span><span class="sxs-lookup"><span data-stu-id="eeead-116">You should be aware of its noncompliance, however.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeead-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eeead-117">See Also</span></span>  
 [<span data-ttu-id="eeead-118">\<PAVE 通过&1;> 编写符合 Cls 的代码</span><span class="sxs-lookup"><span data-stu-id="eeead-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
