---
title: 如何：继承 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 0d8799359a12b9bb64331d83df2500bede8c0ff2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314537"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="0a030-102">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="0a030-102">How to: Inherit Windows Forms</span></span>
<span data-ttu-id="0a030-103">通过从基窗体继承创建新的 Windows 窗体是事半功倍的便捷途径，而每次需要用它时，都无需完全重新创建窗体。</span><span class="sxs-lookup"><span data-stu-id="0a030-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>  
  
 <span data-ttu-id="0a030-104">有关继承窗体在设计时使用的详细信息**继承选择器**对话框以及如何直观地区分的安全级别的继承的控件，请参阅[如何：使用继承选择器对话框继承窗体](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)。</span><span class="sxs-lookup"><span data-stu-id="0a030-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>  
  
 <span data-ttu-id="0a030-105">**请注意**：为了从窗体进行继承，包含该窗体的文件或命名空间必须生成为可执行文件或 DLL。</span><span class="sxs-lookup"><span data-stu-id="0a030-105">**Note** In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="0a030-106">若要生成项目，请从“生成”菜单选择“生成”。</span><span class="sxs-lookup"><span data-stu-id="0a030-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="0a030-107">此外，对命名空间的引用必须添加到继承窗体的类。</span><span class="sxs-lookup"><span data-stu-id="0a030-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span> <span data-ttu-id="0a030-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="0a030-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0a030-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="0a030-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0a030-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="0a030-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-inherit-a-form-programmatically"></a><span data-ttu-id="0a030-111">若要以编程方式继承窗体</span><span class="sxs-lookup"><span data-stu-id="0a030-111">To inherit a form programmatically</span></span>  
  
1. <span data-ttu-id="0a030-112">在类中，添加对命名空间的引用，该命名空间包含想要被继承的窗体。</span><span class="sxs-lookup"><span data-stu-id="0a030-112">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>  
  
2. <span data-ttu-id="0a030-113">在类定义中，将引用添加到将被继承的窗体。</span><span class="sxs-lookup"><span data-stu-id="0a030-113">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="0a030-114">引用应包括包含窗体的命名空间，后跟一个句点，然后是基本窗体本身的名称。</span><span class="sxs-lookup"><span data-stu-id="0a030-114">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 <span data-ttu-id="0a030-115">当继承窗体时，请记住，由于每个事件是由基类和继承类一起进行处理的，所以事件处理程序被调用两次时可能会出现问题。</span><span class="sxs-lookup"><span data-stu-id="0a030-115">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="0a030-116">若要深入了解如何避免此问题，请参阅[有关 Visual Basic 中继承的事件处理程序的疑难解答](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="0a030-116">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a030-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a030-117">See also</span></span>

- [<span data-ttu-id="0a030-118">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="0a030-118">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="0a030-119">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="0a030-119">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="0a030-120">using</span><span class="sxs-lookup"><span data-stu-id="0a030-120">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="0a030-121">修改基窗体的外观的效果</span><span class="sxs-lookup"><span data-stu-id="0a030-121">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="0a030-122">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="0a030-122">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
