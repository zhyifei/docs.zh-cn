---
title: 如何：使用 Modifiers 和 GenerateMember 属性
ms.date: 03/30/2017
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
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211283"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="d7f60-102">如何：使用 Modifiers 和 GenerateMember 属性</span><span class="sxs-lookup"><span data-stu-id="d7f60-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="d7f60-103">当在 Windows 窗体上放置一个组件时，通过在设计环境提供了两个属性：`GenerateMember`和`Modifiers`。</span><span class="sxs-lookup"><span data-stu-id="d7f60-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="d7f60-104">`GenerateMember`属性指定当 Windows 窗体设计器生成的一个组件的成员变量。</span><span class="sxs-lookup"><span data-stu-id="d7f60-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="d7f60-105">`Modifiers`属性是分配给该成员变量的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="d7f60-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="d7f60-106">如果的值`GenerateMember`属性是`false`，则`Modifiers`属性不起作用。</span><span class="sxs-lookup"><span data-stu-id="d7f60-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="d7f60-107">指定组件是否是窗体的成员</span><span class="sxs-lookup"><span data-stu-id="d7f60-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="d7f60-108">在 Visual Studio 中，在 Windows 窗体设计器中，打开你的窗体。</span><span class="sxs-lookup"><span data-stu-id="d7f60-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="d7f60-109">打开**工具箱**，并在窗体上将三个<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="d7f60-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="d7f60-110">设置`GenerateMember`并`Modifiers`每个属性<xref:System.Windows.Forms.Button>根据下表的控件。</span><span class="sxs-lookup"><span data-stu-id="d7f60-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="d7f60-111">按钮名称</span><span class="sxs-lookup"><span data-stu-id="d7f60-111">Button name</span></span>|<span data-ttu-id="d7f60-112">GenerateMember 值</span><span class="sxs-lookup"><span data-stu-id="d7f60-112">GenerateMember value</span></span>|<span data-ttu-id="d7f60-113">修饰符值</span><span class="sxs-lookup"><span data-stu-id="d7f60-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="d7f60-114">无更改</span><span class="sxs-lookup"><span data-stu-id="d7f60-114">No change</span></span>|

4. <span data-ttu-id="d7f60-115">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="d7f60-115">Build the solution.</span></span>

5. <span data-ttu-id="d7f60-116">在“解决方案资源管理器”中，单击“显示所有文件”按钮。</span><span class="sxs-lookup"><span data-stu-id="d7f60-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="d7f60-117">打开**Form1**节点，然后在**代码编辑器**，打开**Form1.Designer.vb**或者**Form1.Designer.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="d7f60-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="d7f60-118">此文件包含 Windows 窗体设计器生成的代码。</span><span class="sxs-lookup"><span data-stu-id="d7f60-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="d7f60-119">找到三个按钮的声明。</span><span class="sxs-lookup"><span data-stu-id="d7f60-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="d7f60-120">下面的代码示例显示了由指定的差异`GenerateMember`和`Modifiers`属性。</span><span class="sxs-lookup"><span data-stu-id="d7f60-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="d7f60-121">默认情况下，Windows 窗体设计器将分配`private`(`Friend`在 Visual Basic 中) 等容器控件的修饰符<xref:System.Windows.Forms.Panel>。</span><span class="sxs-lookup"><span data-stu-id="d7f60-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="d7f60-122">如果您的群<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Form>具有一个容器控件，它不会接受新子级继承的控件和窗体中。</span><span class="sxs-lookup"><span data-stu-id="d7f60-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="d7f60-123">解决方法是更改到基容器控件的修饰符`protected`或`public`。</span><span class="sxs-lookup"><span data-stu-id="d7f60-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7f60-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f60-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="d7f60-125">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="d7f60-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="d7f60-126">演练：演示可视化继承</span><span class="sxs-lookup"><span data-stu-id="d7f60-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="d7f60-127">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="d7f60-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
