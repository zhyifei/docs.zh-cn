---
title: 如何：向 Windows 窗体添加 ActiveX 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 8c4c6c3f96c49401b032e360314794cc800c0551
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987069"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>如何：向 Windows 窗体添加 ActiveX 控件

尽管 Visual Studio 中的 Windows 窗体设计器已优化为承载 Windows 窗体控件, 但你也可以将 ActiveX 控件置于 Windows 窗体上。

> [!CAUTION]
> 向其中添加 ActiveX 控件时, Windows 窗体存在性能限制。

向窗体添加 ActiveX 控件之前, 必须将它们添加到 "工具箱"。 有关详细信息, 请参阅[COM 组件 "自定义工具箱" 对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))。

## <a name="add-an-activex-control-to-your-windows-form"></a>向 Windows 窗体添加 ActiveX 控件

若要向 Windows 窗体添加 ActiveX 控件, 请双击工具箱中的控件。

Visual Studio 会在项目中添加对该控件的所有引用。 有关在 Windows 窗体上使用 ActiveX 控件时要记住的事项的详细信息, 请参阅[在 Windows 窗体上承载 Activex 控件时的注意事项](considerations-when-hosting-an-activex-control-on-a-windows-form.md)。

> [!NOTE]
> Windows 窗体 ActiveX 控件导入程序 (Aximp.exe) 在导入 ActiveX 动态链接库时创建不同类型的事件参数。 Aximp.exe 创建的参数类似于以下内容: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`(如果`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`需要)。 请注意, 此 irregularity 不会阻止代码正常运行。 有关详细信息, 请参阅[Windows 窗体 ActiveX 控件导入程序 (aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)。

## <a name="see-also"></a>请参阅

- [Windows 窗体控件](index.md)
- [不同语言和库中的控件和可编程对象的比较](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
- [标记各个 Windows 窗体控件并创建它们的快捷键](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [按功能列出的 Windows 窗体控件](windows-forms-controls-by-function.md)
