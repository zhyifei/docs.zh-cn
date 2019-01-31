---
title: “<name>”是使用“System.MarshalByRefObject”作为基类的类“<name>”的值类型字段“<classname>”的成员，无法引用
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: c29d3def2299dc1d7e3b084b3408b3f919addc63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279575"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="bb72e-102">不能引用的 '\<名称 > 因为它是值类型字段的成员\<名称 > 的类的\<类名 >' system.marshalbyrefobject 作为基类</span><span class="sxs-lookup"><span data-stu-id="bb72e-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="bb72e-103">`System.MarshalByRefObject`类可让应用程序支持跨应用程序域边界对对象的远程访问。</span><span class="sxs-lookup"><span data-stu-id="bb72e-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="bb72e-104">类型必须继承自`MarshalByRejectObject`类时跨应用程序域边界使用的类型。</span><span class="sxs-lookup"><span data-stu-id="bb72e-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="bb72e-105">不得复制对象的状态，因为对象的成员不是可在其中创建应用程序域之外使用。</span><span class="sxs-lookup"><span data-stu-id="bb72e-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="bb72e-106">**错误 ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="bb72e-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb72e-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bb72e-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="bb72e-108">检查以确保所引用的成员的引用有效。</span><span class="sxs-lookup"><span data-stu-id="bb72e-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="bb72e-109">显式限定的成员`Me`关键字。</span><span class="sxs-lookup"><span data-stu-id="bb72e-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb72e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb72e-110">See also</span></span>
- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="bb72e-111">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="bb72e-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
