---
title: 디자인 타임에 컨트롤 개발
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dac049ea6a51037daa0e23dc93476e4410b2df06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745988"
---
# <a name="develop-windows-forms-controls-at-design-time"></a>在设计时开发 Windows 窗体控件

.NET Framework는 컨트롤 제작자에게 다양한 컨트롤 제작 기술을 제공합니다. 제작자는 더 이상 기존 컨트롤의 컬렉션으로 작동하는 복합 컨트롤을 디자인하도록 제한되지 않습니다. 상속을 통해 기존의 복합 컨트롤 또는 Windows Forms 컨트롤에서 사용자 정의 컨트롤을 만들 수 있습니다. 또한 사용자 지정 그리기를 구현하는 사용자 정의 컨트롤을 디자인할 수 있습니다. 이러한 옵션을 사용하면 시각적 인터페이스의 디자인과 기능에 많은 유연성을 허용할 수 있습니다. 이러한 기능을 이용하려면 개체 지향 프로그래밍 개념을 잘 알고 있어야 합니다.

> [!NOTE]
> 无需透彻地理解继承，但你可能会发现，引用[继承基础知识（Visual Basic）](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)是非常有用的。

Web Forms에서 사용할 사용자 지정 컨트롤을 만들려면 [사용자 지정 ASP.NET 서버 컨트롤 개발](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))을 참조하세요.

## <a name="in-this-section"></a>단원 내용

[演练：创作复合控件](walkthrough-authoring-a-composite-control-with-visual-csharp.md)\
C#에서 간단한 복합 컨트롤을 만드는 방법을 보여 줍니다.

[演练：从 Windows 窗体控件继承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)\
C#에서 상속을 사용하는 간단한 Windows Forms 컨트롤을 만드는 방법을 보여 줍니다.

[演练：使用 Windows 窗体控件上的智能标记执行常见任务](performing-common-tasks-using-smart-tags-on-wf-controls.md)\
Windows Forms 컨트롤에서 스마트 태그 기능을 사용하는 방법을 보여 줍니다.

[演练：用 DesignerSerializationVisibilityAttribute\ 序列化标准类型的集合](serializing-collections-designerserializationvisibilityattribute.md)
演示如何使用 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> 特性序列化集合。

[연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)\
Windows Forms 컨트롤의 디자인 타임 동작을 디버그하는 방법을 보여 줍니다.

[演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)\
복합 컨트롤을 디자인 환경에 긴밀하게 통합하는 방법을 보여 줍니다.

[방법: Windows Forms 컨트롤 작성](how-to-author-controls-for-windows-forms.md)\
Windows Forms 컨트롤을 구현할 때 고려해야 할 사항에 대해 간략하게 설명합니다.

[방법: 합성 컨트롤 제작](how-to-author-composite-controls.md)\
복합 컨트롤에서 상속하여 컨트롤을 만드는 방법을 보여 줍니다.

[방법: UserControl 클래스에서 상속](how-to-inherit-from-the-usercontrol-class.md)\
복합 컨트롤을 만드는 절차에 대해 간략하게 설명합니다.

[방법: 기존 Windows Forms 컨트롤에서 상속](how-to-inherit-from-existing-windows-forms-controls.md)\
演示如何通过从 <xref:System.Windows.Forms.Button> 控件类继承来创建扩展控件。

[방법: Control 클래스에서 상속](how-to-inherit-from-the-control-class.md)\
확장 컨트롤을 만드는 방법에 대해 간략하게 설명합니다.

[如何：在设计时将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)\
演示如何使用 <xref:System.Windows.Forms.Control.Dock%2A> 属性将控件与它所占有窗体的边缘对齐。

[방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)\
**도구 상자 사용자 지정** 대화 상자에 표시되도록 컨트롤을 설치하는 절차를 보여 줍니다.

[如何：为控件提供工具箱位图](how-to-provide-a-toolbox-bitmap-for-a-control.md)\
演示如何使用 <xref:System.Drawing.ToolboxBitmapAttribute> 在**工具箱**中的自定义控件旁边显示一个图标。

[방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)\
**UserControl 테스트 컨테이너**를 사용하여 복합 컨트롤의 동작을 테스트하는 방법을 보여 줍니다.

[Windows Forms 디자이너의 디자인 타임 오류](design-time-errors-in-the-windows-forms-designer.md)\
Windows Forms 디자이너를 로드하지 못할 때 Microsoft Visual Studio에 표시되는 디자인 타임 오류 목록의 의미와 용도에 대해 설명합니다.

[컨트롤 및 구성 요소 작성 문제 해결](troubleshooting-control-and-component-authoring.md)\
사용자 지정 구성 요소 또는 컨트롤을 작성할 때 발생할 수 있는 일반적인 문제를 진단하고 수정하는 방법을 보여 줍니다.

## <a name="reference"></a>참조

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a>관련 단원

[.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](developing-custom-windows-forms-controls.md)\
.NET Framework를 사용하여 사용자 지정 컨트롤을 만드는 방법에 대해 설명합니다.

[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)\
구성 요소의 생성과 사용을 간소화하도록 설계된 공용 언어 런타임을 소개합니다. 이러한 간소화의 중요한 측면은 다양한 프로그래밍 언어를 사용하여 작성된 구성 요소 간의 향상된 상호 운용성에 있습니다. CLS(공용 언어 사양)를 사용하면 여러 프로그래밍 언어를 사용하는 도구와 구성 요소를 만들 수 있습니다.

[연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)\
**도구 상자 사용자 지정** 대화 상자에 구성 요소 또는 컨트롤을 표시하는 방법에 대해 설명합니다.
