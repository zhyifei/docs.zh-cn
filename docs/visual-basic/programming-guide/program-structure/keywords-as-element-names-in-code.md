---
title: 代码中用作元素名称的关键字 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 53c3172e8518115d001c23be2430fbc87ae1b60f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652573"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="e60e0-102">代码中用作元素名称的关键字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e60e0-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="e60e0-103">任何程序元素-例如变量、 类或成员-可以具有相同的名称与受限制的关键字。</span><span class="sxs-lookup"><span data-stu-id="e60e0-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="e60e0-104">例如，可以创建一个名为变量`Loop`。</span><span class="sxs-lookup"><span data-stu-id="e60e0-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="e60e0-105">但是，来指代你版-它具有与同名的受限`Loop`关键字-必须在它前面加上一个完全限定字符串，或将它括在方括号 (`[ ]`)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="e60e0-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 <span data-ttu-id="e60e0-106">如果你不执行其中一种，则 Visual Basic 假设的内部函数的使用`Loop`关键字，并生成错误，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e60e0-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="e60e0-107">在引用窗体和控件，以及时，可以使用方括号声明一个变量或与受限制的关键字定义具有相同名称的过程。</span><span class="sxs-lookup"><span data-stu-id="e60e0-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="e60e0-108">将很容易忘记限定名称或包含方括号，因此将错误引入到你的代码并导致更难以读取。</span><span class="sxs-lookup"><span data-stu-id="e60e0-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="e60e0-109">为此，我们建议你不要将受限制的关键字用作的程序元素的名称。</span><span class="sxs-lookup"><span data-stu-id="e60e0-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="e60e0-110">但是，如果将来版本的 Visual Basic 定义了一个新的关键字冲突，与现有窗体或控件名称，然后你可以使用此方法更新你的代码时要使用新版本。</span><span class="sxs-lookup"><span data-stu-id="e60e0-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e60e0-111">程序还可能包括由其他引用的程序集的元素名称。</span><span class="sxs-lookup"><span data-stu-id="e60e0-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="e60e0-112">如果这些名称与受限制的关键字冲突，然后加上方括号围绕它们会导致 Visual Basic 将解释为您定义的元素。</span><span class="sxs-lookup"><span data-stu-id="e60e0-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60e0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e60e0-113">See Also</span></span>  
 [<span data-ttu-id="e60e0-114">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="e60e0-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="e60e0-115">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="e60e0-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="e60e0-116">关键字</span><span class="sxs-lookup"><span data-stu-id="e60e0-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
