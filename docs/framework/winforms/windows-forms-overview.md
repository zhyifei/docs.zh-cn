---
title: 概述
ms.date: 03/30/2017
helpviewer_keywords:
- smart clients
- Windows Forms, about Windows Forms
ms.assetid: 3a2b6284-c8d6-4e1c-8c69-0bed38f38cd4
ms.openlocfilehash: c3a8394086c9d744630179b089a1f986af12b339
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734548"
---
# <a name="windows-forms-overview"></a>Windows 窗体概述

다음 개요에서는 스마트 클라이언트 애플리케이션의 이점, Windows Forms 프로그래밍의 주요 기능 및 Windows Forms를 사용하여 오늘날의 기업과 최종 사용자의 요구를 충족하는 스마트 클라이언트를 빌드하는 방법을 설명합니다.

## <a name="windows-forms-and-smart-client-apps"></a>Windows 窗体和智能客户端应用

 Windows Forms를 사용하여 스마트 클라이언트를 개발합니다. *스마트 클라이언트*는 쉽게 배포 및 업데이트되며, 인터넷에 연결되었거나 연결이 끊어졌을 때 작동할 수 있고, 기존의 Windows 기반 애플리케이션보다 더 안전하게 로컬 컴퓨터의 리소스에 액세스할 수 있는 시각적으로 풍부한 애플리케이션입니다.

### <a name="build-rich-interactive-user-interfaces"></a>构建丰富的交互式用户界面

 Windows 窗体是一种用于 .NET Framework 的智能客户端技术，这是一组可简化常见应用程序任务（例如，读取和写入文件系统）的托管库。 使用 Visual Studio 之类的开发环境时，可以创建 Windows 窗体智能客户端应用程序，这些应用程序可显示信息、请求来自用户的输入以及通过网络与远程计算机通信。

 Windows Forms에서 *폼*은 정보를 사용자에게 표시하는 비주얼 화면입니다. 일반적으로 폼에 컨트롤을 추가하고 마우스 클릭이나 키 누름과 같은 사용자 동작에 대한 응답을 개발하여 Windows Forms 애플리케이션을 빌드합니다. *컨트롤*은 데이터를 표시하거나 데이터 입력을 수락하는 고유한 UI(사용자 인터페이스) 요소입니다.

 사용자가 폼이나 컨트롤 중 하나에 작업을 수행하면 이벤트가 생성됩니다. 애플리케이션은 코드를 사용하여 이러한 이벤트에 대응하고, 발생 시 이벤트를 처리합니다. 자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](creating-event-handlers-in-windows-forms.md)를 참조하세요.

 Windows Forms에는 텍스트 상자, 단추, 드롭다운 상자, 라디오 단추 및 웹 페이지를 표시하는 컨트롤 등 폼에 추가할 수 있는 다양한 컨트롤이 포함되어 있습니다. 폼에서 사용할 수 있는 모든 컨트롤의 목록은 [Windows Forms에서 사용할 수 있는 컨트롤](./controls/controls-to-use-on-windows-forms.md)을 참조하세요. 기존 컨트롤이 요구를 충족하지 않는 경우 Windows Forms에서 <xref:System.Windows.Forms.UserControl> 클래스를 사용하여 고유한 사용자 지정 컨트롤을 만들 수도 있습니다.

 Windows Forms에는 Microsoft Office와 같은 고급 애플리케이션의 기능을 에뮬레이트하는 풍부한 UI 컨트롤이 있습니다. <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하는 경우 텍스트와 이미지를 포함하고, 하위 메뉴를 표시하며, 텍스트 상자 및 콤보 상자와 같은 기타 컨트롤을 호스트하는 도구 모음과 메뉴를 만들 수 있습니다.

 通过在 Visual Studio 中进行拖放**Windows 窗体设计器**，可以轻松创建 Windows 窗体应用程序。 커서를 사용하여 컨트롤을 선택하고 폼에서 원하는 위치에 추가하면 됩니다. 디자이너는 컨트롤을 쉽게 배치하기 위한 모눈선 및 맞춤선과 같은 도구를 제공합니다. 无论您是使用 Visual Studio 还是在命令行上编译，都可以使用 <xref:System.Windows.Forms.FlowLayoutPanel>、<xref:System.Windows.Forms.TableLayoutPanel> 和 <xref:System.Windows.Forms.SplitContainer> 控件以更少的时间创建高级窗体布局。

 끝으로, 고유한 사용자 지정 UI 요소를 만들어야 하는 경우 <xref:System.Drawing> 네임스페이스에는 선, 원 및 기타 도형을 폼에 직접 렌더링하는 다양한 클래스가 포함되어 있습니다.

> [!NOTE]
> Windows Forms 컨트롤은 애플리케이션 도메인 간에 마샬링되도록 설계되어 있지 않습니다. 이런 이유로 Microsoft는 <xref:System.MarshalByRefObject>의 <xref:System.Windows.Controls.Control> 기본 형식이 가능한 것처럼 표시해도 <xref:System.AppDomain> 경계를 넘어서 Windows Forms 컨트롤을 전달하는 기능을 지원하지 않습니다. 애플리케이션 도메인 경계를 넘어서 Windows Forms 컨트롤이 전달되지 않는 한 여러 개의 애플리케이션 도메인을 가진 Windows Forms 애플리케이션이 지원됩니다.

#### <a name="create-forms-and-controls"></a>创建窗体和控件

이러한 기능을 사용하는 방법에 대한 단계별 정보는 다음 도움말 항목을 참조하세요.

|설명|도움말 항목|
|-----------------|----------------|
|폼에서 컨트롤 사용|[방법: Windows Forms에 컨트롤 추가](./controls/how-to-add-controls-to-windows-forms.md)|
|<xref:System.Windows.Forms.ToolStrip> 컨트롤 사용|[방법: 디자이너를 사용하여 표준 항목이 있는 기본 ToolStrip 만들기](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md)|
|<xref:System.Drawing>을 사용하여 그래픽 만들기|[그래픽 프로그래밍 시작](./advanced/getting-started-with-graphics-programming.md)|
|사용자 지정 컨트롤 만들기|[방법: UserControl 클래스에서 상속](./controls/how-to-inherit-from-the-usercontrol-class.md)|

### <a name="display-and-manipulate-data"></a>显示和操作数据
 많은 애플리케이션은 데이터베이스, XML 파일, XML Web services 또는 기타 데이터 소스의 데이터를 표시해야 합니다. Windows Forms는 각 데이터 조각이 해당 셀을 사용하도록 이러한 표 형식 데이터를 기존의 행과 열 형식으로 표시하기 위해 <xref:System.Windows.Forms.DataGridView> 컨트롤이라는 유연한 컨트롤을 제공합니다. <xref:System.Windows.Forms.DataGridView>를 사용하는 경우 다른 기능 중에서도 개별 셀의 모양을 사용자 지정하고, 임의의 행과 열을 제자리에 잠그고, 셀 안에 복잡한 컨트롤을 표시할 수 있습니다.

 네트워크를 통해 데이터 소스에 연결하는 것은 Windows Forms 스마트 클라이언트에서 간단한 작업입니다. <xref:System.Windows.Forms.BindingSource> 组件表示与数据源的连接，并公开用于将数据绑定到控件的方法，导航到上一个和下一个记录，编辑记录，并将更改保存回原始源。 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 통해 사용자가 레코드를 탐색하기 위한 간단한 인터페이스를 제공합니다.

 데이터 소스 창을 통해 데이터 바인딩된 컨트롤을 쉽게 만들 수 있습니다. 창에는 데이터베이스, 웹 서비스 및 개체와 같은 프로젝트의 데이터 소스가 표시됩니다. 이 창에서 프로젝트의 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다. 데이터 소스 창에서 기존 컨트롤로 개체를 끌어 기존 컨트롤을 데이터에 바인딩할 수도 있습니다.

 Windows Forms에서 관리할 수 있는 다른 형식의 데이터 바인딩은 *설정*입니다. 대부분의 스마트 클라이언트 애플리케이션은 마지막으로 알려진 폼 크기와 같은 런타임 상태에 대한 일부 정보를 유지하고 저장된 파일의 기본 위치와 같은 사용자 기본 설정 데이터를 유지해야 합니다. 애플리케이션 설정 기능은 클라이언트 컴퓨터에 두 유형의 설정을 모두 쉽게 저장할 수 있는 방법을 제공하여 이러한 요구 사항을 충족합니다. 使用 Visual Studio 或代码编辑器定义这些设置后，这些设置将作为 XML 保留，并在运行时自动读回到内存中。

#### <a name="display-and-manipulate-data"></a>显示和操作数据

이러한 기능을 사용하는 방법에 대한 단계별 정보는 다음 도움말 항목을 참조하세요.

|설명|도움말 항목|
|-----------------|----------------|
|<xref:System.Windows.Forms.BindingSource> 구성 요소 사용|[방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩](./controls/bind-wf-controls-with-the-bindingsource.md)|
|使用 ADO.NET 数据源|[방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|데이터 소스 창 사용|[Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)|
|애플리케이션 설정 사용|[방법: 애플리케이션 설정 만들기](./advanced/how-to-create-application-settings.md)|

### <a name="deploy-apps-to-client-computers"></a>将应用部署到客户端计算机

애플리케이션을 작성한 후 해당 클라이언트 컴퓨터에 설치하고 실행할 수 있도록 사용자에게 애플리케이션을 보내야 합니다. 使用 ClickOnce 技术时，只需单击几下鼠标，就能从 Visual Studio 中部署应用程序，并向用户提供指向 Web 上的应用程序的 URL。 ClickOnce 管理应用程序中的所有元素和依赖项，并确保应用程序正确安装在客户端计算机上。

ClickOnce 应用程序可以配置为仅在用户连接到网络时运行，或者在联机和脱机状态下运行。 如果指定应用程序应支持脱机操作，则 ClickOnce 会在用户的 "**开始**" 菜单中添加一个指向应用程序的链接。 그러면 사용자가 URL을 사용하지 않고도 애플리케이션을 열 수 있습니다.

애플리케이션을 업데이트하는 경우 새 배포 매니페스트와 애플리케이션의 새 복사본을 웹 서버에 게시합니다. ClickOnce 将检测到有可用更新，并升级用户的安装;更新旧程序集无需进行自定义编程。

#### <a name="deploy-clickonce-apps"></a>部署 ClickOnce 应用

有关 ClickOnce 的完整介绍，请参阅[Clickonce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。 이러한 기능을 사용하는 방법에 대한 단계별 정보는 다음 도움말 항목을 참조하세요.

|설명|도움말 항목|
|-----------------|----------------|
|使用 ClickOnce 部署应用程序|[방법: 게시 마법사를 사용하여 ClickOnce 애플리케이션 게시](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [연습: ClickOnce 애플리케이션 수동 배포](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|更新 ClickOnce 部署|[방법: ClickOnce 애플리케이션에 대한 업데이트 관리](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|用 ClickOnce 管理安全性|[방법: ClickOnce 보안 설정 사용](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

### <a name="other-controls-and-features"></a>其他控件和功能

Windows Forms에는 대화 상자 만들기, 인쇄, 도움말 및 설명서 추가 및 여러 언어로 애플리케이션 지역화 지원과 같이 일반적인 작업을 쉽고 빠르게 구현할 수 있게 해주는 다른 여러 기능이 있습니다. 此外，Windows 窗体依赖于 .NET Framework 的强大安全系统。 이 시스템을 통해 보다 안전한 애플리케이션을 고객에게 릴리스할 수 있습니다.

#### <a name="implement-other-controls-and-features"></a>实现其他控件和功能

이러한 기능을 사용하는 방법에 대한 단계별 정보는 다음 도움말 항목을 참조하세요.

|설명|도움말 항목|
|-----------------|----------------|
|폼의 콘텐츠 인쇄|[방법: Windows Forms의 그래픽 인쇄](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Windows Forms 보안에 대한 자세한 정보|[Windows Forms의 보안 개요](security-in-windows-forms-overview.md)|

## <a name="see-also"></a>另请参阅

- [Windows Forms 시작](getting-started-with-windows-forms.md)
- [새 Windows Form 만들기](creating-a-new-windows-form.md)
- [ToolStrip 컨트롤 개요](./controls/toolstrip-control-overview-windows-forms.md)
- [DataGridView 컨트롤 개요](./controls/datagridview-control-overview-windows-forms.md)
- [BindingSource 구성 요소 개요](./controls/bindingsource-component-overview.md)
- [애플리케이션 설정 개요](./advanced/application-settings-overview.md)
- [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)
