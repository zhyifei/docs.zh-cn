---
title: 类型&lt;typename&gt;不符合 CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 9911b4fe7b88996f17cb5e9eec7d4a5f2c254b76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594603"
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="9ed03-102">类型&lt;typename&gt;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="9ed03-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="9ed03-103">变量、 属性或函数返回声明具有不符合 CLS 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9ed03-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="9ed03-104">应用程序，以符合[语言独立性和独立于语言的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)，它必须只使用符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="9ed03-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="9ed03-105">下面的 Visual Basic 数据类型不符合 cls 的：</span><span class="sxs-lookup"><span data-stu-id="9ed03-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="9ed03-106">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="9ed03-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="9ed03-107">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="9ed03-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="9ed03-108">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="9ed03-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="9ed03-109">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="9ed03-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="9ed03-110">**错误 ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="9ed03-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ed03-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9ed03-111">To correct this error</span></span>  
  
-   <span data-ttu-id="9ed03-112">如果你的应用程序需要符合 cls 的将此元素的数据类型更改为最接近的符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="9ed03-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="9ed03-113">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="9ed03-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="9ed03-114">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="9ed03-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="9ed03-115">如果你的应用程序并不需要符合 cls 的你不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="9ed03-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="9ed03-116">你应注意它是不符合，但是。</span><span class="sxs-lookup"><span data-stu-id="9ed03-116">You should be aware of its noncompliance, however.</span></span>