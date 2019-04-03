---
title: 应为初始值设定项
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 77cfeb57bc313ded2d2c4d5a0c59041c5c19f515
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826075"
---
# <a name="initializer-expected"></a><span data-ttu-id="d7b81-102">应为初始值设定项</span><span class="sxs-lookup"><span data-stu-id="d7b81-102">Initializer expected</span></span>
<span data-ttu-id="d7b81-103">已尝试通过使用对象初始值设定项中的初始化列表为空，如下面的示例中所示声明类的实例。</span><span class="sxs-lookup"><span data-stu-id="d7b81-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="d7b81-104">下面的示例中所示，必须在初始值设定项列表中，初始化至少一个字段或属性。</span><span class="sxs-lookup"><span data-stu-id="d7b81-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="d7b81-105">**错误 ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="d7b81-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d7b81-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d7b81-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d7b81-107">初始化至少一个字段或属性初始值设定项，或不使用对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="d7b81-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b81-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7b81-108">See also</span></span>

- [<span data-ttu-id="d7b81-109">对象初始值设定项：命名和匿名类型</span><span class="sxs-lookup"><span data-stu-id="d7b81-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="d7b81-110">如何：使用对象初始值设定项声明对象</span><span class="sxs-lookup"><span data-stu-id="d7b81-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
