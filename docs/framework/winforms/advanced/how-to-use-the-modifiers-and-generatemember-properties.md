---
title: "如何：使用 Modifiers 和 GenerateMember 属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f524bab55527bf9d3c744cb6f50d1df1fc9a2302
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="bd16f-102">如何：使用 Modifiers 和 GenerateMember 属性</span><span class="sxs-lookup"><span data-stu-id="bd16f-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="bd16f-103">当将一个组件放在 Windows 窗体上时，由设计环境提供两个属性：`GenerateMember`和`Modifiers`。</span><span class="sxs-lookup"><span data-stu-id="bd16f-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="bd16f-104">`GenerateMember`属性指定当 Windows 窗体设计器生成的组件的成员变量。</span><span class="sxs-lookup"><span data-stu-id="bd16f-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="bd16f-105">`Modifiers`属性是分配给该成员变量的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="bd16f-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="bd16f-106">如果值`GenerateMember`属性是`false`的值`Modifiers`属性不起作用。</span><span class="sxs-lookup"><span data-stu-id="bd16f-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd16f-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="bd16f-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bd16f-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="bd16f-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bd16f-109">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="bd16f-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="bd16f-110">若要指定组件是否为窗体的成员</span><span class="sxs-lookup"><span data-stu-id="bd16f-110">To specify whether a component is a member of the form</span></span>  
  
1.  <span data-ttu-id="bd16f-111">在 Windows 窗体设计器中，打开你的窗体。</span><span class="sxs-lookup"><span data-stu-id="bd16f-111">In the Windows Forms Designer, open your form.</span></span>  
  
2.  <span data-ttu-id="bd16f-112">打开**工具箱**，并在表单中，将三个<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="bd16f-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3.  <span data-ttu-id="bd16f-113">设置`GenerateMember`和`Modifiers`每个属性<xref:System.Windows.Forms.Button>根据下表的控件。</span><span class="sxs-lookup"><span data-stu-id="bd16f-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="bd16f-114">按钮名称</span><span class="sxs-lookup"><span data-stu-id="bd16f-114">Button name</span></span>|<span data-ttu-id="bd16f-115">GenerateMember 值</span><span class="sxs-lookup"><span data-stu-id="bd16f-115">GenerateMember value</span></span>|<span data-ttu-id="bd16f-116">修饰符值</span><span class="sxs-lookup"><span data-stu-id="bd16f-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="bd16f-117">无更改</span><span class="sxs-lookup"><span data-stu-id="bd16f-117">No change</span></span>|  
  
4.  <span data-ttu-id="bd16f-118">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="bd16f-118">Build the solution.</span></span>  
  
5.  <span data-ttu-id="bd16f-119">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="bd16f-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6.  <span data-ttu-id="bd16f-120">打开**Form1**节点，然后在**代码编辑器**，打开**Form1.Designer.vb**或**Form1.Designer.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="bd16f-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="bd16f-121">此文件包含由 Windows 窗体设计器发出的代码。</span><span class="sxs-lookup"><span data-stu-id="bd16f-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7.  <span data-ttu-id="bd16f-122">找到三个按钮的声明。</span><span class="sxs-lookup"><span data-stu-id="bd16f-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="bd16f-123">下面的代码示例显示由指定的差异`GenerateMember`和`Modifiers`属性。</span><span class="sxs-lookup"><span data-stu-id="bd16f-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="bd16f-124">默认情况下，Windows 窗体设计器会分配`private`(`Friend`在 Visual Basic 中) 修饰符添加到容器控件，例如构造<xref:System.Windows.Forms.Panel>。</span><span class="sxs-lookup"><span data-stu-id="bd16f-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="bd16f-125">如果你基<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Form>具有容器的控件，它将不接受新子类别继承的控件和窗体中。</span><span class="sxs-lookup"><span data-stu-id="bd16f-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="bd16f-126">解决方案是更改该基容器控件的修饰符`protected`或`public`。</span><span class="sxs-lookup"><span data-stu-id="bd16f-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd16f-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd16f-127">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="bd16f-128">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="bd16f-128">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [<span data-ttu-id="bd16f-129">演练：演示可视化继承</span><span class="sxs-lookup"><span data-stu-id="bd16f-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [<span data-ttu-id="bd16f-130">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="bd16f-130">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
