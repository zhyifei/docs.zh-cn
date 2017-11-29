---
title: "&#39;&lt;关键字&gt;&#39; 只能在实例方法内有效"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords: BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a61314c036cec0fd1412a9c844a610fbd1401add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="98e3e-102">&#39;&lt;关键字&gt;&#39; 只能在实例方法内有效</span><span class="sxs-lookup"><span data-stu-id="98e3e-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="98e3e-103">`Me`， `MyClass`，和`MyBase`关键字引用特定的类实例。</span><span class="sxs-lookup"><span data-stu-id="98e3e-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="98e3e-104">你无法使用其内部共享`Function`或`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="98e3e-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="98e3e-105">**错误 ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="98e3e-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="98e3e-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="98e3e-106">To correct this error</span></span>  
  
-   <span data-ttu-id="98e3e-107">从过程中删除关键字或删除`Shared`从过程声明的关键字。</span><span class="sxs-lookup"><span data-stu-id="98e3e-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e3e-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98e3e-108">See Also</span></span>  
 [<span data-ttu-id="98e3e-109">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="98e3e-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="98e3e-110">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="98e3e-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="98e3e-111">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="98e3e-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
