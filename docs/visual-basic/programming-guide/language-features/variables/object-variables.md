---
title: Visual Basic 中的对象变量
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 8383261c1806732c4c8abea9834000f003a848a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649108"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="01b24-102">Visual Basic 中的对象变量</span><span class="sxs-lookup"><span data-stu-id="01b24-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="01b24-103">除了直接存储值，变量还可以引用的对象。</span><span class="sxs-lookup"><span data-stu-id="01b24-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="01b24-104">出于相同原因向变量分配任何值，可以向变量分配一个对象：</span><span class="sxs-lookup"><span data-stu-id="01b24-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="01b24-105">变量名称通常是更短且易于记住比的方法和属性访问的对象本身所需的完整路径。</span><span class="sxs-lookup"><span data-stu-id="01b24-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="01b24-106">使用引用的对象的变量是比重复通过所需的方法或属性访问的对象本身更高效。</span><span class="sxs-lookup"><span data-stu-id="01b24-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="01b24-107">你可以更改一个变量来运行你的代码时引用其他对象。</span><span class="sxs-lookup"><span data-stu-id="01b24-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="01b24-108">使代码更短</span><span class="sxs-lookup"><span data-stu-id="01b24-108">Making Code Shorter</span></span>  
 <span data-ttu-id="01b24-109">可以使用对象变量来缩短的代码，你已为类型。</span><span class="sxs-lookup"><span data-stu-id="01b24-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="01b24-110">下面的示例使用方法和属性的完整路径访问<xref:System.Windows.Forms.Control>对象。</span><span class="sxs-lookup"><span data-stu-id="01b24-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="01b24-111">你可以缩短此代码中，并加快执行，如果你使用的对象变量进行控制。</span><span class="sxs-lookup"><span data-stu-id="01b24-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="01b24-112">你应声明对象变量与你想要向其分配特定类 (`Control`在这种情况下)。</span><span class="sxs-lookup"><span data-stu-id="01b24-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="01b24-113">一旦你将对象分配给该变量时，你可以它完全相同的方式来处理将它所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="01b24-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="01b24-114">你可以设置或检索该对象的属性或使用任何其方法。</span><span class="sxs-lookup"><span data-stu-id="01b24-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="01b24-115">下面的示例使用对象变量来简化在前面的示例代码。</span><span class="sxs-lookup"><span data-stu-id="01b24-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="01b24-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="01b24-116">See Also</span></span>  
 [<span data-ttu-id="01b24-117">变量声明</span><span class="sxs-lookup"><span data-stu-id="01b24-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="01b24-118">如何：加速访问具有长限定路径的对象</span><span class="sxs-lookup"><span data-stu-id="01b24-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [<span data-ttu-id="01b24-119">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="01b24-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="01b24-120">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="01b24-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="01b24-121">对象变量值</span><span class="sxs-lookup"><span data-stu-id="01b24-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
