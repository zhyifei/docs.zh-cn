---
title: "&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;membername&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords: BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="60b85-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;membername&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="60b85-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="60b85-103">\<类型名称 > 必须实现\<成员名称 > 接口\<n a m e >。</span><span class="sxs-lookup"><span data-stu-id="60b85-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="60b85-104">实现属性必须拥有匹配的 ReadOnly / WriteOnly 说明符。</span><span class="sxs-lookup"><span data-stu-id="60b85-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="60b85-105">类或结构实现接口声明，但不实现过程、 属性或由接口定义的事件。</span><span class="sxs-lookup"><span data-stu-id="60b85-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="60b85-106">必须实现该接口的每个成员。</span><span class="sxs-lookup"><span data-stu-id="60b85-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="60b85-107">**错误 ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="60b85-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60b85-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="60b85-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="60b85-109">声明具有相同的名称和签名在接口中定义的成员。</span><span class="sxs-lookup"><span data-stu-id="60b85-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="60b85-110">请务必包括至少`End Function`， `End Sub`，或`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="60b85-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="60b85-111">添加`Implements`子句的末尾`Function`， `Sub`， `Property`，或`Event`语句。</span><span class="sxs-lookup"><span data-stu-id="60b85-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="60b85-112">例如：</span><span class="sxs-lookup"><span data-stu-id="60b85-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="60b85-113">在实施一个属性，请确保`ReadOnly`或`WriteOnly`中与接口定义相同的方式使用。</span><span class="sxs-lookup"><span data-stu-id="60b85-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="60b85-114">当实现一个属性，将声明`Get`和`Set`于相应过程。</span><span class="sxs-lookup"><span data-stu-id="60b85-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b85-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60b85-115">See Also</span></span>  
 [<span data-ttu-id="60b85-116">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="60b85-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="60b85-117">接口</span><span class="sxs-lookup"><span data-stu-id="60b85-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
