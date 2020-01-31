---
title: 开发一个简单的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 5383cee5358dbd260fc6c023d3db607da6b10ea4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742252"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>如何：开发简单的 Windows 窗体控件

本部分演示创建自定义 Windows 窗体控件的关键步骤。 本演练中开发的简单控件允许更改其 <xref:System.Windows.Forms.Control.Text%2A> 属性的对齐方式。 它不会引发或处理事件。

### <a name="to-create-a-simple-custom-control"></a>创建简单的自定义控件

1. 定义一个从 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 派生的类。

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. 定义属性。 （不需要定义属性，因为控件继承了 <xref:System.Windows.Forms.Control> 类中的多个属性，但大多数自定义控件通常都定义了其他属性。）下面的代码段定义了一个名为 `TextAlignment` 的属性，`FirstControl` 使用该属性设置从 <xref:System.Windows.Forms.Control>继承的 <xref:System.Windows.Forms.Control.Text%2A> 属性的显示格式。 有关定义属性的详细信息，请参阅[属性概述](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120))。

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     设置更改控件可视显示的属性时，必须调用 <xref:System.Windows.Forms.Control.Invalidate%2A> 方法来重绘控件。 在基类 <xref:System.Windows.Forms.Control>中定义 <xref:System.Windows.Forms.Control.Invalidate%2A>。

3. 重写从 <xref:System.Windows.Forms.Control> 继承的受保护的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，为控件提供呈现逻辑。 如果不重写 <xref:System.Windows.Forms.Control.OnPaint%2A>，则控件将无法绘制自身。 在下面的代码片段中，<xref:System.Windows.Forms.Control.OnPaint%2A> 方法显示从 <xref:System.Windows.Forms.Control> 继承的 <xref:System.Windows.Forms.Control.Text%2A> 属性与 `alignmentValue` 字段指定的对齐方式。

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. 为控件提供属性。 特性让视觉设计器能够在设计时适当显示控件及其属性和事件。 以下代码片段将特性应用于 `TextAlignment` 属性。 在 Visual Studio 之类的设计器中，<xref:System.ComponentModel.CategoryAttribute.Category%2A> 特性（显示在代码段中）使属性显示在逻辑类别下。 选择 `TextAlignment` 属性时，<xref:System.ComponentModel.DescriptionAttribute.Description%2A> 特性会导致在 "**属性**" 窗口的底部显示描述性字符串。 有关属性的详细信息，请参阅[组件的设计时属性](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))。

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. （可选）为控件提供资源。 可通过使用编译器选项（对于 C#，为 `/res`）将资源和控件进行打包，从而为控件提供资源（如位图）。 在运行时，可以使用 <xref:System.Resources.ResourceManager> 类的方法检索资源。 有关创建和使用资源的详细信息，请参阅[桌面应用中的资源](../../resources/index.md)。

6. 编译和部署控件。 要编译和部署 `FirstControl,`，请执行以下步骤：

    1. 将以下示例中的代码保存到源文件（如 FirstControl.cs 或 FirstControl.vb）。

    2. 将源代码编译成程序集并将其保存在应用程序的目录中。 要完成此操作，请从包含源文件的目录执行以下命令。

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         `/t:library` 编译器选项会告知编译器正在创建的程序集是库（而不是可执行文件）。 `/out` 选项指定程序集的路径和名称。 `/r` 选项提供代码引用的程序集的名称。 在此示例中，将创建只有你的应用程序可以使用的私有程序集。 因此，必须将其保存在应用程序的目录中。 有关打包和部署控件以进行分发的详细信息，请参阅[部署](../../deployment/index.md)。

此示例演示了 `FirstControl` 的代码。 控件包含在命名空间 `CustomWinControls` 中。 命名空间提供相关类型的逻辑分组。 可在新的或现有命名空间中创建控件。 在 C# 中，`using` 声明（在 Visual Basic 中，为 `Imports`）允许从命名空间访问类型，而无需使用类型的完全限定名称。 在下面的示例中，`using` 声明允许代码从 <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.Control> 直接访问类 <xref:System.Windows.Forms.Control>，而不必使用完全限定名称 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>。

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a>在窗体上使用自定义控件

以下示例显示使用 `FirstControl` 的简单窗体。 它会创建 `FirstControl` 的三个实例，每个实例具有一个不同的 `TextAlignment` 属性值。

#### <a name="to-compile-and-run-this-sample"></a>编译和运行此示例

1. 将以下示例中的代码保存到源文件（SimpleForm.cs 或 SimpleForms.vb）。

2. 通过从包含源文件的目录执行以下命令，将源代码编译成可执行程序集。

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     CustomWinControls 是包含 `FirstControl`的类的程序集。 此程序集必须与访问程序集的窗体的源文件（SimpleForm.cs或SimpleForms.vb）位于同一目录中。

3. 使用以下命令执行 SimpleForm.exe。

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a>另请参阅

- [Windows 窗体控件中的属性](properties-in-windows-forms-controls.md)
- [Windows 窗体控件中的事件](events-in-windows-forms-controls.md)
