---
title: "&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;methodname&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords: BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e803ec7d0054f2fa1b9ed2a731fd30c9c3060468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="bec4b-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;methodname&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="bec4b-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="bec4b-103">类或结构实现接口声明，但不实现由接口定义的过程。</span><span class="sxs-lookup"><span data-stu-id="bec4b-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="bec4b-104">必须实现该接口的每个成员。</span><span class="sxs-lookup"><span data-stu-id="bec4b-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="bec4b-105">**错误 ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="bec4b-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bec4b-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bec4b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="bec4b-107">声明具有相同的名称和签名在接口中定义的过程。</span><span class="sxs-lookup"><span data-stu-id="bec4b-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="bec4b-108">请务必包括至少`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="bec4b-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="bec4b-109">添加`Implements`子句的末尾`Function`或`Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="bec4b-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="bec4b-110">例如: </span><span class="sxs-lookup"><span data-stu-id="bec4b-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bec4b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bec4b-111">See Also</span></span>  
 [<span data-ttu-id="bec4b-112">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="bec4b-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="bec4b-113">接口</span><span class="sxs-lookup"><span data-stu-id="bec4b-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
