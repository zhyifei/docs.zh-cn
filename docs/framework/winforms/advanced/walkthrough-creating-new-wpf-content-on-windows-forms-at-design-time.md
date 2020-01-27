---
title: 在 Windows 窗体上创建新的 WPF 内容
titleSuffix: ''
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 69a0598b05d1b2bff84b203317d6d5a166ce109d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746387"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a>演练：在设计时在 Windows 窗体上创建新的 WPF 内容

本文介绍如何创建 Windows Presentation Foundation （WPF）控件，以便在基于 Windows 窗体的应用程序中使用。

## <a name="prerequisites"></a>先决条件

이 연습을 완료하려면 Visual Studio가 필요합니다.

## <a name="create-the-project"></a>프로젝트를 만듭니다.

打开 Visual Studio，并在 Visual Basic 或 Visual C#命名 `HostingWpf`中创建新的**Windows 窗体应用程序（.NET Framework）** 项目。

> [!NOTE]
> WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.

## <a name="create-a-new-wpf-control"></a>创建新的 WPF 控件

새 WPF 컨트롤을 만들고 프로젝트에 추가하는 작업은 다른 항목을 프로젝트에 추가하는 것만큼 쉽습니다. Windows 窗体设计器使用名为*复合控件*或*用户控件*的特定类型控件。 WPF 사용자 정의 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.UserControl>을 참조하세요.

> [!NOTE]
> WPF용 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 형식은 Windows Forms에서 제공하는 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>이라는 사용자 정의 컨트롤 형식과 별개입니다.

若要创建新的 WPF 控件：

1. 在**解决方案资源管理器**中，将一个新的**WPF 用户控件库（.NET Framework）** 项目添加到解决方案。 컨트롤 라이브러리의 기본 이름인 `WpfControlLibrary1`을 사용합니다. 기본 컨트롤 이름은 `UserControl1.xaml`입니다.

   添加新控件具有以下效果：

   - UserControl1.xaml 파일이 추가됩니다.

   - 添加文件 UserControl1.xaml.cs （或 UserControl1）。 이 파일에는 이벤트 처리기 및 기타 구현에 대한 코드 숨김이 포함됩니다.

   - WPF 어셈블리에 대한 참조가 추가됩니다.

   - 文件 UserControl1 在 Visual Studio 的 WPF 设计器中打开。

2. 디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.

3. 在 "**属性**" 窗口中，将 "<xref:System.Windows.FrameworkElement.Width%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性的值设置为**200**。

4. 从 "**工具箱**" 中，将 "<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>" 控件拖动到设计图面上。

5. 在 "**属性**" 窗口中，将 "<xref:System.Windows.Controls.TextBox.Text%2A>" 属性的值设置为 "**托管内容**"。

   > [!NOTE]
   > 일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.

6. 프로젝트를 빌드합니다.

## <a name="add-a-wpf-control-to-a-windows-form"></a>将 WPF 控件添加到 Windows 窗体

폼에서 새 WPF 컨트롤을 사용할 준비가 되었습니다. Windows 窗体使用 <xref:System.Windows.Forms.Integration.ElementHost> 控件来承载 WPF 内容。

若要将 WPF 控件添加到 Windows 窗体：

1. Windows Forms 디자이너에서 `Form1`을 엽니다.

2. 在 "**工具箱**" 中，找到标记为 " **WPFUserControlLibrary WPF 用户控件**" 的选项卡。

3. `UserControl1` 인스턴스를 폼으로 끕니다.

    - WPF 컨트롤을 호스트할 폼에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자동으로 만들어집니다.

    - <xref:System.Windows.Forms.Integration.ElementHost> 控件被命名为 `elementHost1` 并在 "**属性**" 窗口中，可以看到其 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 属性设置为 " **UserControl1**"。

    - WPF 어셈블리에 대한 참조가 프로젝트에 추가됩니다.

    - `elementHost1` 컨트롤에는 사용 가능한 호스팅 옵션을 표시하는 스마트 태그 패널이 있습니다.

4. 在 " **ElementHost 任务**" 智能标记面板中，选择 "**在父容器中停靠**"。

5. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

## <a name="next-steps"></a>后续步骤

Windows Forms와 WPF는 서로 다른 기술이지만 긴밀하게 상호 운용하도록 설계되었습니다. 若要在应用程序中提供更丰富的外观和行为，请尝试以下操作：

- WPF 페이지에서 Windows Forms 컨트롤을 호스트합니다. 有关详细信息，请参阅[演练：在 WPF 中承载 Windows 窗体控件](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)。

- WPF 콘텐츠에 Windows Forms 시각적 스타일을 적용합니다. 자세한 내용은 [방법: 혼합 애플리케이션에서 비주얼 스타일 사용](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)을 참조하세요.

- WPF 콘텐츠의 스타일을 변경합니다. 有关详细信息，请参阅[演练：设置 WPF 内容的样式](walkthrough-styling-wpf-content.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [마이그레이션 및 상호 운용성](../../wpf/advanced/migration-and-interoperability.md)
- [WPF 컨트롤 사용](using-wpf-controls.md)
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
