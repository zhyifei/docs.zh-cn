---
title: '&lt;type1&gt;&#39;&lt;typename&gt; &#39;必须实现&#39; &lt;methodname&gt; &#39;接口&#39; &lt;n a m e&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: daeeab853f6a7f582542fa15ffc09ce749731d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594378"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a><span data-ttu-id="6bd0e-102">&lt;type1&gt;&#39;&lt;typename&gt; &#39;必须实现&#39; &lt;methodname&gt; &#39;接口&#39; &lt;n a m e&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="6bd0e-102">&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;</span></span>
<span data-ttu-id="6bd0e-103">类或结构实现接口声明，但不实现由接口定义的过程。</span><span class="sxs-lookup"><span data-stu-id="6bd0e-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="6bd0e-104">必须实现该接口的每个成员。</span><span class="sxs-lookup"><span data-stu-id="6bd0e-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="6bd0e-105">**错误 ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="6bd0e-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6bd0e-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="6bd0e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="6bd0e-107">声明具有相同的名称和签名在接口中定义的过程。</span><span class="sxs-lookup"><span data-stu-id="6bd0e-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="6bd0e-108">请务必包括至少`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="6bd0e-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="6bd0e-109">添加`Implements`子句的末尾`Function`或`Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="6bd0e-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="6bd0e-110">例如：</span><span class="sxs-lookup"><span data-stu-id="6bd0e-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6bd0e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bd0e-111">See Also</span></span>  
 [<span data-ttu-id="6bd0e-112">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="6bd0e-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="6bd0e-113">接口</span><span class="sxs-lookup"><span data-stu-id="6bd0e-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
