---
title: "演练：演示可视化继承"
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
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c5ef33be9841b5c74b6ae2448daf56079489b61
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>演练：演示可视化继承
通过 Visual 继承，可以查看基本表单上的控件和添加新控件。 在本演练中，你将创建基窗体，并将其编译到类库。 将此类库导入另一个项目，并创建一个从基窗体继承的新窗体。 在本演练中，你将学会如何执行以下任务：  
  
-   创建包含基窗体的类库项目。  
  
-   添加具有可修改基窗体的派生类的属性的按钮。  
  
-   添加基窗体的继承者无法修改的按钮。  
  
-   创建包含从 `BaseForm` 继承的窗体的项目。  
  
 最后，本演练将显示继承的窗体上私有控件和受保护控件之间的差异。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
> [!CAUTION]
>  并非所有控件都支持从基窗体执行 Visual 继承。 以下控件不支持本演练中描述的情景：  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  无论使用何种修饰符（`private``protected` 或 `public`），继承的窗体中的这些控件始终为只读。  
  
## <a name="scenario-steps"></a>方案步骤  
 第一步是创建基窗体。  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a>创建包含基窗体的类库项目  
  
1.  从**文件**菜单上，选择**新建**，，然后**项目**以打开**新项目**对话框。  
  
2.  创建 Windows 窗体应用程序名为`BaseFormLibrary`。  
  
3.  若要在中创建一个类库，而不是标准的 Windows 窗体应用程序，**解决方案资源管理器**，右键单击**BaseFormLibrary**项目节点，然后选择**属性**.  
  
4.  在项目属性中，更改**输出类型**从**Windows 应用程序**到**类库**。  
  
5.  从**文件**菜单上，选择**保存所有**将项目和文件保存到默认位置。  
  
 接下来的两步是将按钮添加至基窗体。 为了演示 visual 继承，请通过设置按钮的 `Modifiers` 属性为它们指定不同的访问级别。  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a>添加基窗体的继承者可修改的按钮  
  
1.  打开**Form1**设计器中。  
  
2.  上**所有 Windows 窗体**选项卡**工具箱**，双击**按钮**到窗体添加一个按钮。 使用鼠标来定位按钮和调整其大小。  
  
3.  在“属性”窗口中，设置按钮的下列属性：  
  
    -   设置**文本**属性**Say Hello**。  
  
    -   设置**（名称）**属性**btnProtected**。  
  
    -   设置**修饰符**属性**受保护**。 这使得继承的窗体**Form1**若要修改的属性**btnProtected**。  
  
4.  双击**Say Hello**按钮以添加事件处理程序**单击**事件。  
  
5.  将以下代码行添加到事件处理程序：  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>添加基窗体的继承者不能修改的按钮  
  
1.  切换到设计视图，通过单击**Form1.vb [设计]，Form1.cs [Design]，or Form1.jsl [Design]**选项卡上方代码编辑器中，或按 F7。  
  
2.  按如下方式添加第二个按钮并设置其属性：  
  
    -   设置**文本**属性**Say Goodbye**。  
  
    -   设置**（名称）**属性**btnPrivate**。  
  
    -   设置**修饰符**属性**私有**。 这使继承的窗体**Form1**若要修改的属性**btnPrivate**。  
  
3.  双击**Say Goodbye**按钮以添加事件处理程序**单击**事件。 将以下代码行放入事件过程：  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  从**生成**菜单上，选择**构建 BaseForm 库**生成类库。  
  
     构建库后，可创建从刚创建的窗体继承的新项目。  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>创建包含继承自基窗体的窗体的项目  
  
1.  从**文件**菜单上，选择**添加**然后**新项目**以打开**添加新项目**对话框。  
  
2.  创建 Windows 窗体应用程序名为`InheritanceTest`。  
  
#### <a name="to-add-an-inherited-form"></a>添加继承的窗体  
  
1.  在**解决方案资源管理器**，右键单击**InheritanceTest**项目，依次选择**添加**，然后选择**新项**。  
  
2.  在**添加新项**对话框中，选择**Windows 窗体**类别 （如果你有一个类别的列表），然后选择**继承的窗体**模板。  
  
3.  保留默认名称的`Form2`，然后单击**添加**。  
  
4.  在**继承选择器**对话框中，选择**Form1**从**BaseFormLibrary**项目中的，表单能够从继承并单击用作**确定**.  
  
     这将创建中的窗体**InheritanceTest**派生自的窗体中的项目**BaseFormLibrary**。  
  
5.  打开继承的窗体 (**Form2**) 通过双击它，如果尚未打开设计器中。  
  
     继承的按钮在设计器中，有一个符号 (![VisualBasicInheritanceSymbol 屏幕快照](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) 在其上角，指示它们继承。  
  
6.  选择**Say Hello**按钮，然后观察调整大小图柄。 由于此按钮受保护，继承者可以对其进行移动、调整大小、更改标题和进行其他修改。  
  
7.  选择个人**Say Goodbye**按钮，并请注意它不具有调整大小图柄。 此外，在**属性**窗口中，此按钮的属性呈灰显，指示不能修改它们。  
  
8.  如果使用 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]：  
  
    1.  在**解决方案资源管理器**，右键单击**Form1**中**InheritanceTest**项目，然后选择**删除**。 在显示的消息框中，单击**确定**以确认删除。  
  
    2.  打开 Program.cs 文件并将 `Application.Run(new Form1());` 行更改为 `Application.Run(new Form2());`。  
  
9. 在**解决方案资源管理器**，右键单击**InheritanceTest**项目，然后选择**设为启动项目**。  
  
10. 在**解决方案资源管理器**，右键单击**InheritanceTest**项目，然后选择**属性**。  
  
11. 在**InheritanceTest**属性页中，设置**启动对象**要继承的窗体 (**Form2**)。  
  
12. 按 F5 运行此应用程序，并观察继承的窗体的行为。  
  
## <a name="next-steps"></a>后续步骤  
 用户控件的继承方式大致相同。 打开新的类库项目并添加用户控件。 在其上放置构成控件，然后编译项目。 打开另一个新的类库项目，并添加对已编译的类库的引用。 另外，尝试将继承的控件 (通过**添加新项**对话框) 到项目和使用**继承选择器**。 添加用户控件，并更改 `Inherits`（[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 中的 `:`）语句。 有关详细信息，请参阅[如何： 继承 Windows 窗体](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何：继承 Windows 窗体](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Windows 窗体可视化继承](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Windows 窗体](../../../../docs/framework/winforms/index.md)
