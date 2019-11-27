---
title: 对象变量
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 7eb860bc732f923316b8ce1d7b94ecdb368bfec3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351782"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="a5080-102">Visual Basic 中的对象变量</span><span class="sxs-lookup"><span data-stu-id="a5080-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="a5080-103">除了直接存储值以外，变量还可以引用对象。</span><span class="sxs-lookup"><span data-stu-id="a5080-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="a5080-104">将对象分配给变量的原因与将任何值分配给变量的原因相同：</span><span class="sxs-lookup"><span data-stu-id="a5080-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="a5080-105">变量名通常比访问对象本身所需的方法和属性的完整路径更短且更易于记忆。</span><span class="sxs-lookup"><span data-stu-id="a5080-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="a5080-106">使用引用对象的变量比通过所需的方法或属性重复访问对象本身更为有效。</span><span class="sxs-lookup"><span data-stu-id="a5080-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="a5080-107">在代码运行时，可以更改变量以引用其他对象。</span><span class="sxs-lookup"><span data-stu-id="a5080-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="a5080-108">使代码更短</span><span class="sxs-lookup"><span data-stu-id="a5080-108">Making Code Shorter</span></span>

<span data-ttu-id="a5080-109">可以使用对象变量缩短需要键入的代码。</span><span class="sxs-lookup"><span data-stu-id="a5080-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="a5080-110">下面的示例使用方法和属性的完整路径来访问 <xref:System.Windows.Forms.Control> 对象。</span><span class="sxs-lookup"><span data-stu-id="a5080-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="a5080-111">如果对控件使用对象变量，则可缩短此代码并加快执行速度。</span><span class="sxs-lookup"><span data-stu-id="a5080-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="a5080-112">应将对象变量声明为要分配给它的特定类（在此示例中为`Control`）。</span><span class="sxs-lookup"><span data-stu-id="a5080-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="a5080-113">将对象分配给变量后，可以将其视为与处理它所引用的对象完全相同。</span><span class="sxs-lookup"><span data-stu-id="a5080-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="a5080-114">可以设置或检索对象的属性或使用其任何方法。</span><span class="sxs-lookup"><span data-stu-id="a5080-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="a5080-115">下面的示例使用对象变量来简化前面的示例中的代码。</span><span class="sxs-lookup"><span data-stu-id="a5080-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="a5080-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5080-116">See also</span></span>

- [<span data-ttu-id="a5080-117">变量声明</span><span class="sxs-lookup"><span data-stu-id="a5080-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="a5080-118">如何：加速访问具有长限定路径的对象</span><span class="sxs-lookup"><span data-stu-id="a5080-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="a5080-119">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="a5080-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="a5080-120">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="a5080-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="a5080-121">对象变量值</span><span class="sxs-lookup"><span data-stu-id="a5080-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
