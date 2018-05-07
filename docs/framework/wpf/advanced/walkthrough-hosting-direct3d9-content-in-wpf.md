---
title: 演练：在 WPF 中承载 Direct3D9 内容
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 3b215c0eead8c5fc28b477b81f75c39b5c946302
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>演练：在 WPF 中承载 Direct3D9 内容
本演练演示如何承载 Direct3D9 Windows Presentation Foundation (WPF) 应用程序中的内容。  
  
 在本演练中，你将要执行以下任务：  
  
-   创建用于承载 Direct3D9 内容的 WPF 项目。  
  
-   导入 Direct3D9 内容。  
  
-   通过使用显示 Direct3D9 内容<xref:System.Windows.Interop.D3DImage>类。  
  
 当完成后时，你将知道如何承载 Direct3D9 内容在 WPF 应用程序。  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]。  
  
-   DirectX 9 或更高版本的 SDK。  
  
-   包含 Direct3D9 内容中的 WPF 兼容格式的 DLL。 有关详细信息，请参阅[WPF 和 Direct3D9 间的互操作](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)和[演练： 创建内容的 WPF 中的托管的 Direct3D9](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)。  
  
## <a name="creating-the-wpf-project"></a>创建 WPF 项目  
 第一步是创建 WPF 应用程序的项目。  
  
#### <a name="to-create-the-wpf-project"></a>创建 WPF 项目  
  
-   新的 WPF 应用程序项目中 Visual C# 创建名为`D3DHost`。 有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。  
  
     在中，打开 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。  
  
## <a name="importing-the-direct3d9-content"></a>导入 Direct3D9 内容  
 使用导入 Direct3D9 内容从非托管 DLL`DllImport`属性。  
  
#### <a name="to-import-direct3d9-content"></a>若要导入 Direct3D9 内容  
  
1.  在代码编辑器中打开 MainWindow.xaml.cs。  
  
2.  自动生成的代码替换为以下代码。  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>承载 Direct3D9 内容  
 最后，使用<xref:System.Windows.Interop.D3DImage>类来承载 Direct3D9 的内容。  
  
#### <a name="to-host-the-direct3d9-content"></a>要承载 Direct3D9 内容  
  
1.  在 MainWindow.xaml 中，替换下面的 XAML 自动生成的 XAML。  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  生成项目。  
  
3.  将复制包含 bin/Debug 文件夹将 Direct3D9 内容的 DLL。  
  
4.  按 F5 运行项目。  
  
     Direct3D9 内容出现在 WPF 应用程序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Interop.D3DImage>  
 [Direct3D9 和 WPF 互操作性的性能注意事项](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
