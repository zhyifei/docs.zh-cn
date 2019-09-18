---
title: 演练：在 WPF 中承载 Direct3D9 内容
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 2c31c044aa50a74255a61da1675037ab3d09f615
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053452"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>演练：在 WPF 中承载 Direct3D9 内容

本演练演示如何在 Windows Presentation Foundation （WPF）应用程序中承载 Direct3D9 内容。

在本演练中，你将要执行以下任务：

- 创建用于托管 Direct3D9 内容的 WPF 项目。

- 导入 Direct3D9 内容。

- 使用<xref:System.Windows.Interop.D3DImage>类显示 Direct3D9 内容。

 完成后，你将了解如何在 WPF 应用程序中托管 Direct3D9 内容。

## <a name="prerequisites"></a>系统必备

你需要以下组件来完成本演练：

- Visual Studio。

- DirectX SDK 9 或更高版本。

- 一个 DLL，其中包含与 WPF 兼容的格式的 Direct3D9 内容。 有关详细信息，请参阅[WPF 和 Direct3D9 互操作](wpf-and-direct3d9-interoperation.md)和[演练：创建用于在 WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)中承载的 Direct3D9 内容。

## <a name="creating-the-wpf-project"></a>创建 WPF 项目

第一步是创建 WPF 应用程序的项目。

### <a name="to-create-the-wpf-project"></a>创建 WPF 项目

在视觉对象C#中创建一个名为`D3DHost`的新 WPF 应用程序项目。 有关详细信息，请参见[演练：我的第一个 WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)桌面应用程序。

Mainwindow.xaml 在中[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]打开。

## <a name="importing-the-direct3d9-content"></a>导入 Direct3D9 内容

使用`DllImport`属性从非托管 DLL 导入 Direct3D9 内容。

### <a name="to-import-direct3d9-content"></a>导入 Direct3D9 内容

1. 在代码编辑器中打开 MainWindow.xaml.cs。

2. 将自动生成的代码替换为以下代码。

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a>承载 Direct3D9 内容

最后，使用<xref:System.Windows.Interop.D3DImage>类来承载 Direct3D9 内容。

### <a name="to-host-the-direct3d9-content"></a>承载 Direct3D9 内容

1. 在 Mainwindow.xaml 中，将自动生成的 XAML 替换为以下 XAML。

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. 生成项目。

3. 将包含 Direct3D9 内容的 DLL 复制到 bin/Debug 文件夹。

4. 按 F5 运行项目。

    Direct3D9 内容显示在 WPF 应用程序中。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.D3DImage>
- [Direct3D9 和 WPF 互操作性的性能注意事项](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
