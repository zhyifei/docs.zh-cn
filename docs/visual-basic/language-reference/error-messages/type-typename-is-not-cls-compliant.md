---
title: "类型&lt;typename&gt;不符合 CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords: BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d45da3b061dff0f82c1155daf5724033261bbdaa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="4ab74-102">类型&lt;typename&gt;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="4ab74-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="4ab74-103">变量、 属性或函数返回声明具有不符合 CLS 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="4ab74-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="4ab74-104">应用程序，以符合[语言独立性和独立于语言的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，它必须只使用符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="4ab74-104">For an application to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="4ab74-105">以下 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 数据类型不符合 CLS：</span><span class="sxs-lookup"><span data-stu-id="4ab74-105">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="4ab74-106">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="4ab74-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="4ab74-107">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="4ab74-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="4ab74-108">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="4ab74-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="4ab74-109">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="4ab74-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="4ab74-110">**错误 ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="4ab74-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4ab74-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4ab74-111">To correct this error</span></span>  
  
-   <span data-ttu-id="4ab74-112">如果你的应用程序需要符合 cls 的将此元素的数据类型更改为最接近的符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="4ab74-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="4ab74-113">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="4ab74-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="4ab74-114">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="4ab74-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="4ab74-115">如果你的应用程序并不需要符合 cls 的你不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="4ab74-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="4ab74-116">你应注意它是不符合，但是。</span><span class="sxs-lookup"><span data-stu-id="4ab74-116">You should be aware of its noncompliance, however.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab74-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab74-117">See Also</span></span>  
 [<span data-ttu-id="4ab74-118">\<PAVE 通过 > 编写符合 Cls 的代码</span><span class="sxs-lookup"><span data-stu-id="4ab74-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
