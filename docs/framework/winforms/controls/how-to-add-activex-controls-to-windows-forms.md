---
title: 如何：向 Windows 窗体添加 ActiveX 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 17311adade187ef3c8e4e639299e6c5cbbcd98a9
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210394"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>如何：向 Windows 窗体添加 ActiveX 控件

虽然 Visual Studio 中的 Windows 窗体设计器已经过优化，承载 Windows 窗体控件，还可以将 Windows 窗体上的 ActiveX 控件。

> [!CAUTION]
> ActiveX 控件添加到它们时，有有关 Windows 窗体的性能限制。

向窗体添加 ActiveX 控件之前，必须将它们添加到工具箱。 有关详细信息，请参阅[COM 组件、 自定义工具箱对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))。

## <a name="add-an-activex-control-to-your-windows-form"></a>向 Windows 窗体添加 ActiveX 控件

若要向 Windows 窗体添加 ActiveX 控件，请双击工具箱上的控件。

Visual Studio 项目中添加对该控件的所有引用。 使用 Windows 窗体上的 ActiveX 控件时，需要注意的事项的详细信息，请参阅[承载 Windows 窗体上的 ActiveX 控件时的注意事项](considerations-when-hosting-an-activex-control-on-a-windows-form.md)。

> [!NOTE]
> Windows 窗体 ActiveX 控件导入程序 (AxImp.exe) 比预期的 ActiveX 动态链接库导入后创建其他类型的事件参数。 AxImp.exe 所创建的参数，如下所示： `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`，当`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`预期。 请注意，此不一致情况不会阻止代码工作正常。 有关详细信息，请参阅[Windows 窗体 ActiveX 控件导入程序 (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)。

## <a name="see-also"></a>请参阅

- [Windows 窗体控件](index.md)
- [不同语言和库中的控件和可编程对象的比较](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
- [在 Windows 窗体上排列控件](arranging-controls-on-windows-forms.md)
- [标记各个 Windows 窗体控件并创建它们的快捷键](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [按功能列出的 Windows 窗体控件](windows-forms-controls-by-function.md)
