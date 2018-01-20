---
title: "如何：向 Windows 窗体添加 ActiveX 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 940dd21fc48c23ce623280aab2c487db5810057c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>如何：向 Windows 窗体添加 ActiveX 控件
虽然 Windows 窗体设计器已经过优化，主机 Windows 窗体控件，您还可将 Windows 窗体上的 ActiveX 控件。  
  
> [!CAUTION]
>  ActiveX 控件添加到它们时，有一些 Windows 窗体的性能限制。  
  
 在向窗体添加 ActiveX 控件之前，必须将它们添加到工具箱中。 有关详细信息，请参阅[COM 组件、 自定义工具箱对话框](http://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请单击 **“工具”** 菜单上的 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>若要向 Windows 窗体添加 ActiveX 控件  
  
-   双击工具箱上的控件。  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]在你的项目中添加到控件的所有引用。 使用 Windows 窗体上的 ActiveX 控件时，需要注意的事项的详细信息，请参阅[承载 Windows 窗体上的 ActiveX 控件时的注意事项](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md)。  
  
    > [!NOTE]
    >  Windows 窗体 ActiveX 控件导入程序 (AxImp.exe) 创建不同类型的事件自变量比预期时 ActiveX 动态链接库中导入。 AxImp.exe 所创建的自变量是类似于以下： `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`，当`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`预期。 请注意，此不一致情况不会阻止代码工作正常。 有关详细信息，请参阅[Windows 窗体 ActiveX 控件导入程序 (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [不同语言和库中的控件和可编程对象的比较](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
