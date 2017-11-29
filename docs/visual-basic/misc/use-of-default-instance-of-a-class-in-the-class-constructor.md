---
title: "在类构造函数中使用类的默认实例可能会导致无限递归调用"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a0c54c6e62f9bdc7fe510500a486461d26636d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="af128-102">在类构造函数中使用类的默认实例可能会导致无限递归调用</span><span class="sxs-lookup"><span data-stu-id="af128-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="af128-103">已在类的构造函数中使用类的默认实例。</span><span class="sxs-lookup"><span data-stu-id="af128-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="af128-104">这可能会导致无限递归调用（也称为无限循环）。</span><span class="sxs-lookup"><span data-stu-id="af128-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="af128-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="af128-105">To correct this error</span></span>  
  
-   <span data-ttu-id="af128-106">从类构造函数中删除默认实例。</span><span class="sxs-lookup"><span data-stu-id="af128-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af128-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af128-107">See Also</span></span>  
 [<span data-ttu-id="af128-108">构造函数</span><span class="sxs-lookup"><span data-stu-id="af128-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
