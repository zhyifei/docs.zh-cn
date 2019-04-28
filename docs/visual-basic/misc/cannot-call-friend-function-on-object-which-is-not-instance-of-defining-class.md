---
title: 在不是定义类的实例的对象上不能调用友元函数
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c65bbb5028cf042b702bb2b8336d40512c980790
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912686"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="f7b71-102">在不是定义类的实例的对象上不能调用友元函数</span><span class="sxs-lookup"><span data-stu-id="f7b71-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="f7b71-103">尝试调用某个类的 `Friend` 过程，或者尝试跨进程或跨线程访问 `Friend` 属性或方法。</span><span class="sxs-lookup"><span data-stu-id="f7b71-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="f7b71-104">`Friend` 过程可从类外部的模块中调用，但该模块是在其中定义该类的项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="f7b71-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7b71-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f7b71-105">To correct this error</span></span>  
  
- <span data-ttu-id="f7b71-106">确保从模块中调用或访问该过程，此模块是在其中定义该类的项目的一部分。</span><span class="sxs-lookup"><span data-stu-id="f7b71-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b71-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7b71-107">See also</span></span>

- [<span data-ttu-id="f7b71-108">Friend</span><span class="sxs-lookup"><span data-stu-id="f7b71-108">Friend</span></span>](../../visual-basic/language-reference/modifiers/friend.md)
