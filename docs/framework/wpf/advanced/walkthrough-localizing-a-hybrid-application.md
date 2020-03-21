---
title: 演练：本地化混合应用程序
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111109"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>演练：本地化混合应用程序

本演练将介绍如何本地化[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]基于 Windows 窗体的混合应用程序中的元素。

本演练涉及以下任务：

- 创建 Windows 窗体主机项目。

- 添加可本地化的内容。

- 启用本地化。

- 分配资源标识符。

- 使用 LocBaml 工具生成附属程序集。

有关本演练中说明的任务的完整代码列表，请参阅[本地化混合应用程序示例](https://go.microsoft.com/fwlink/?LinkID=160015)。

完成后，你将拥有一个本地化的混合应用程序。

## <a name="prerequisites"></a>系统必备

您需要满足以下条件才能完成本演练：

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>创建 Windows 窗体宿主项目

第一步是创建 Windows 窗体应用程序项目，并添加包含[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]要本地化的内容的元素。

### <a name="to-create-the-host-project"></a>创建宿主项目

1. 创建名为`LocalizingWpfInWf`**的 WPF 应用**项目。  （**文件** > **新项目** > **Project** > **Classic Desktop** > **WPF Application****Visual Basic****Visual C#** 可视化C#或可视化基本经典桌面WPF应用程序）。 > 

2. 向项目[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl>添加调用`SimpleControl`的元素。

3. 使用<xref:System.Windows.Forms.Integration.ElementHost>控件在窗体上`SimpleControl`放置元素。 有关详细信息，请参阅[演练：在 Windows 窗体中托管 3D WPF 复合控件](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)。

## <a name="adding-localizable-content"></a>添加可本地化的内容

接下来，您将添加 Windows 窗体标签控件，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]并将元素的内容设置为可本地化字符串。

### <a name="to-add-localizable-content"></a>添加可本地化的内容

1. 在**解决方案资源管理器中**，双击**SimpleControl.xaml**以在 WPF 设计器中打开它。

2. 使用以下代码设置<xref:System.Windows.Controls.Button>控件的内容。

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. 在**解决方案资源管理器中**，双击**Form1**以在 Windows 窗体设计器中打开它。

4. 打开**工具箱**并双击**标签**以向窗体添加标签控件。 将其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值设置为 `"Hello"`。

5. 按**F5**生成并运行应用程序。

     元素`SimpleControl`和标签控件都显示文本 **"你好"。**

## <a name="enabling-localization"></a>启用本地化

Windows 窗体设计器提供用于在附属程序集中启用本地化的设置。

### <a name="to-enable-localization"></a>启用本地化

1. 在**解决方案资源管理器**中，双击**Form1.cs**在 Windows 窗体设计器中打开它。

2. 在 **"属性"** 窗口中，将窗体的**可本地化**属性的值设置为`true`。

3. 在 **"属性"** 窗口中，将**语言**属性的值设置为**西班牙语（西班牙）。**

4. 在 Windows 窗体设计器中，选择标签控件。

5. 在 **"属性"** 窗口中，将<xref:System.Windows.Forms.Control.Text%2A>属性的值设置为`"Hola"`。

     一个名为 Form1.es-ES.resx 的新资源文件会添加到项目中。

6. 在**解决方案资源管理器**中，右键单击**Form1.cs**并单击 **"查看代码**"以在代码编辑器中打开它。

7. 将以下代码复制到构造函数`Form1`中，在调用 之前到`InitializeComponent`。

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. 在**解决方案资源管理器中**，右键单击 **"本地化 WpfinWf"，** 然后单击 **"卸载项目**"。

     项目名称标记为 **（不可用）。**

9. 右键单击 **"本地化 WpfinWf**"，然后单击 **"编辑本地化 WpfinWf.csproj**"。

     项目文件将在代码编辑器中打开。

10. 将以下行复制到项目文件中的第`PropertyGroup`一行。

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. 保存项目文件并将其关闭。

12. 在**解决方案资源管理器中**，右键单击 **"本地化 WpfinWf"，** 然后单击 **"重新加载项目**"。

## <a name="assigning-resource-identifiers"></a>分配资源标识符

可以通过使用资源标识符将可本地化内容映射到资源程序集。 当您指定`updateuid`选项时，MsBuild.exe 应用程序会自动分配资源标识符。

### <a name="to-assign-resource-identifiers"></a>分配资源标识符

1. 从"开始"菜单中，打开可视化工作室的开发人员命令提示。

2. 使用以下命令将资源标识符分配到可本地化内容。

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. 在**解决方案资源管理器中**，双击**SimpleControl.xaml**以在代码编辑器中打开它。 您将看到该`msbuild`命令已将`Uid`该属性添加到所有元素。 这有助于通过分配资源标识符进行本地化。

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. 按 **F6** 以生成解决方案。

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>使用 LocBaml 生成附属程序集

本地化的内容存储在仅资源附属*程序集*中。 使用命令行工具 LocBaml.exe 为您的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容生成本地化程序集。

### <a name="to-produce-a-satellite-assembly"></a>生成附属程序集

1. 将 LocBaml.exe 复制到项目的 obj\Debug 文件夹中。 有关详细信息，请参阅[本地化应用程序](how-to-localize-an-application.md)。

2. 在“命令提示符”窗口中，使用以下命令将资源字符串提取到临时文件中。

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. 使用 Visual Studio 或其他文本编辑器打开 temp.csv 文件。 将字符串`"Hello"`替换为其西班牙语翻译 。 `"Hola"`

4. 保存 temp.csv 文件。

5. 使用以下命令生成本地化资源文件。

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     将在 obj\Debug 文件夹中创建 LocalizingWpfInWf.g.es-ES.resources 文件。

6. 使用以下命令生成本地化附属程序集。

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     将在 obj\Debug 文件夹中创建 LocalizingWpfInWf.resources.dll 文件。

7. 将 LocalizingWpfInWf.resources.dll 文件复制到项目的 bin\Debug\es-ES 文件夹中。 替换现有文件。

8. 运行 LocalizingWpfInWf.exe，它位于项目的 bin\Debug 文件夹中。 不要重新生成应用程序，否则附属程序集将被覆盖。

     应用程序显示本地化后的字符串，而不是英语字符串。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [本地化应用程序](how-to-localize-an-application.md)
- [演练：本地化 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
