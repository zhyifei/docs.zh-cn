---
title: 如何：使对象变量不引用任何实例
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352886"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="42ff2-102">如何：使对象变量不引用任何实例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42ff2-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="42ff2-103">您可以通过将对象变量设置为 "[无](../../../../visual-basic/language-reference/nothing.md)" 来解除对象变量与任何对象实例的关联。</span><span class="sxs-lookup"><span data-stu-id="42ff2-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="42ff2-104">断开对象变量与任何对象实例的关联</span><span class="sxs-lookup"><span data-stu-id="42ff2-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="42ff2-105">在赋值语句中，将变量设置为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="42ff2-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="42ff2-106">可靠的编程</span><span class="sxs-lookup"><span data-stu-id="42ff2-106">Robust Programming</span></span>  
 <span data-ttu-id="42ff2-107">如果你的代码尝试访问已设置为 `Nothing`的对象变量的成员，则会发生 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="42ff2-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="42ff2-108">如果将某个对象变量设置为经常 `Nothing`，或者变量未初始化，则最好将成员访问包含在 `Try...Catch...Finally` 块中。</span><span class="sxs-lookup"><span data-stu-id="42ff2-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="42ff2-109">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="42ff2-109">.NET Framework Security</span></span>  
 <span data-ttu-id="42ff2-110">如果对包含机密数据或敏感数据的对象使用对象变量，则在不主动处理这些对象之一时，可以将变量设置为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="42ff2-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="42ff2-111">这减少了恶意代码访问数据的可能性。</span><span class="sxs-lookup"><span data-stu-id="42ff2-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ff2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42ff2-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="42ff2-113">对象变量</span><span class="sxs-lookup"><span data-stu-id="42ff2-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="42ff2-114">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="42ff2-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="42ff2-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="42ff2-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="42ff2-116">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="42ff2-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
