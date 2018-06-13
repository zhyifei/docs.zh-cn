---
title: 应为初始值设定项
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 9d786fd1e929129c420b7bec62efd0bd445d85eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586381"
---
# <a name="initializer-expected"></a><span data-ttu-id="d5b51-102">应为初始值设定项</span><span class="sxs-lookup"><span data-stu-id="d5b51-102">Initializer expected</span></span>
<span data-ttu-id="d5b51-103">您试图使用在其中初始化列表为空，下面的示例中所示的对象初始值设定项声明类的实例。</span><span class="sxs-lookup"><span data-stu-id="d5b51-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="d5b51-104">下面的示例中所示，必须在初始值设定项列表中，初始化至少一个字段或属性。</span><span class="sxs-lookup"><span data-stu-id="d5b51-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="d5b51-105">**错误 ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="d5b51-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5b51-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d5b51-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d5b51-107">初始化至少一个字段或属性初始值设定项，或者不使用对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="d5b51-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b51-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5b51-108">See Also</span></span>  
 [<span data-ttu-id="d5b51-109">对象初始值设定项：命名类型和匿名类型</span><span class="sxs-lookup"><span data-stu-id="d5b51-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="d5b51-110">如何：使用对象初始值设定项声明对象</span><span class="sxs-lookup"><span data-stu-id="d5b51-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
