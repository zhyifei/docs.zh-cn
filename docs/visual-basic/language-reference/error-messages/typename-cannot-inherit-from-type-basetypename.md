---
title: “<typename>”将对基 <type> 的访问扩展到程序集的外部，因此无法从 <basetypename>“<type>”继承
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: e21eea20d953e64e91522074c25f037451145bf8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664214"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="703ee-102">\<类型名称 > 不能继承自\<类型 >\<基类型名称 > 扩展的基本访问权限，因此\<类型 > 程序集外部的</span><span class="sxs-lookup"><span data-stu-id="703ee-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="703ee-103">类或接口继承自的基类或接口但具有限制性较弱的访问级别。</span><span class="sxs-lookup"><span data-stu-id="703ee-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="703ee-104">例如，`Public`接口继承自`Friend`接口，或`Protected`类继承自`Private`类。</span><span class="sxs-lookup"><span data-stu-id="703ee-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="703ee-105">这会公开的基类或接口来访问超出了预期的级别。</span><span class="sxs-lookup"><span data-stu-id="703ee-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="703ee-106">**错误 ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="703ee-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="703ee-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="703ee-107">To correct this error</span></span>  
  
- <span data-ttu-id="703ee-108">更改派生的类或接口的基类或接口至少限制的访问级别。</span><span class="sxs-lookup"><span data-stu-id="703ee-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="703ee-109">或</span><span class="sxs-lookup"><span data-stu-id="703ee-109">-or-</span></span>  
  
- <span data-ttu-id="703ee-110">如果需要限制较少的访问级别，请删除`Inherits`语句。</span><span class="sxs-lookup"><span data-stu-id="703ee-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="703ee-111">不能从更受限制的基类或接口继承。</span><span class="sxs-lookup"><span data-stu-id="703ee-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703ee-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="703ee-112">See also</span></span>

- [<span data-ttu-id="703ee-113">Class 语句</span><span class="sxs-lookup"><span data-stu-id="703ee-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="703ee-114">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="703ee-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="703ee-115">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="703ee-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="703ee-116">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="703ee-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
