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
ms.openlocfilehash: f11595daac74ceb76c5d017af015d5523506bdf3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>如何：使用 Modifiers 和 GenerateMember 属性
当将一个组件放在 Windows 窗体上时，由设计环境提供两个属性：`GenerateMember`和`Modifiers`。 `GenerateMember`属性指定当 Windows 窗体设计器生成的组件的成员变量。 `Modifiers`属性是分配给该成员变量的访问修饰符。 如果值`GenerateMember`属性是`false`的值`Modifiers`属性不起作用。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a>若要指定组件是否为窗体的成员  
  
1.  在 Windows 窗体设计器中，打开你的窗体。  
  
2.  打开**工具箱**，并在表单中，将三个<xref:System.Windows.Forms.Button>控件。  
  
3.  设置`GenerateMember`和`Modifiers`每个属性<xref:System.Windows.Forms.Button>根据下表的控件。  
  
    |按钮名称|GenerateMember 值|修饰符值|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|无更改|  
  
4.  生成解决方案。  
  
5.  在“解决方案资源管理器”中，单击“显示所有文件”按钮。  
  
6.  打开**Form1**节点，然后在**代码编辑器**，打开**Form1.Designer.vb**或**Form1.Designer.cs**文件。 此文件包含由 Windows 窗体设计器发出的代码。  
  
7.  找到三个按钮的声明。 下面的代码示例显示由指定的差异`GenerateMember`和`Modifiers`属性。  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  默认情况下，Windows 窗体设计器会分配`private`(`Friend`在 Visual Basic 中) 修饰符添加到容器控件，例如构造<xref:System.Windows.Forms.Panel>。 如果你基<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Form>具有容器的控件，它将不接受新子类别继承的控件和窗体中。 解决方案是更改该基容器控件的修饰符`protected`或`public`。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Button>  
 [Windows 窗体可视化继承](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [演练：演示可视化继承](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [如何：继承 Windows 窗体](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
