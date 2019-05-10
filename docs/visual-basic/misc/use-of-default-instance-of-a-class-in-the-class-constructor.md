---
title: 在类构造函数中使用类的默认实例可能会导致无限递归调用
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 1cad1e3cf3943e945d519aee061a877c91684b4a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623472"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="b02eb-102">在类构造函数中使用类的默认实例可能会导致无限递归调用</span><span class="sxs-lookup"><span data-stu-id="b02eb-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="b02eb-103">已在类的构造函数中使用类的默认实例。</span><span class="sxs-lookup"><span data-stu-id="b02eb-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="b02eb-104">这可能会导致无限递归调用（也称为无限循环）。</span><span class="sxs-lookup"><span data-stu-id="b02eb-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b02eb-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b02eb-105">To correct this error</span></span>  
  
- <span data-ttu-id="b02eb-106">从类构造函数中删除默认实例。</span><span class="sxs-lookup"><span data-stu-id="b02eb-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02eb-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="b02eb-107">See also</span></span>

- [<span data-ttu-id="b02eb-108">构造函数</span><span class="sxs-lookup"><span data-stu-id="b02eb-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
