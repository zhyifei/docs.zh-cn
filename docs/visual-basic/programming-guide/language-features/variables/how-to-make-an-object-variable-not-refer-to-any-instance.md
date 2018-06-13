---
title: 如何：使对象变量不引用任何实例 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: bf918b762261e1dd1fc4161a10203f3d0067e454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649719"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="4d126-102">如何：使对象变量不引用任何实例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d126-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="4d126-103">你可以通过将它设置为解除关联，从任何对象实例的对象变量[执行任何操作](../../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="4d126-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="4d126-104">若要解除关联从任何对象实例的对象变量</span><span class="sxs-lookup"><span data-stu-id="4d126-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="4d126-105">将变量设置为`Nothing`在赋值语句中。</span><span class="sxs-lookup"><span data-stu-id="4d126-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="4d126-106">可靠编程</span><span class="sxs-lookup"><span data-stu-id="4d126-106">Robust Programming</span></span>  
 <span data-ttu-id="4d126-107">如果你的代码尝试访问已被设置为对象变量的成员`Nothing`、<xref:System.NullReferenceException>时发生。</span><span class="sxs-lookup"><span data-stu-id="4d126-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="4d126-108">如果对象变量设置为`Nothing`频繁，或者如果可能未初始化变量，则最好将中的成员访问包含`Try...Catch...Finally`块。</span><span class="sxs-lookup"><span data-stu-id="4d126-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4d126-109">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="4d126-109">.NET Framework Security</span></span>  
 <span data-ttu-id="4d126-110">如果你用于包含机密或敏感数据的对象使用的对象变量，可以将变量设置为`Nothing`时你不主动处理的那些对象之一。</span><span class="sxs-lookup"><span data-stu-id="4d126-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="4d126-111">这可以减少访问数据的恶意代码的机会。</span><span class="sxs-lookup"><span data-stu-id="4d126-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d126-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d126-112">See Also</span></span>  
 <xref:System.NullReferenceException>  
 [<span data-ttu-id="4d126-113">对象变量</span><span class="sxs-lookup"><span data-stu-id="4d126-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="4d126-114">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="4d126-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="4d126-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="4d126-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="4d126-116">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="4d126-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="4d126-117">异常疑难解答：System.NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="4d126-117">Troubleshooting Exceptions: System.NullReferenceException</span></span>](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
