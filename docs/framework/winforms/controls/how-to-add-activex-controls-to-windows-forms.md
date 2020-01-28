---
title: 向窗体添加 ActiveX 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 920c1111a5703352a4b624068e3d5ceae9892591
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746845"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="dc8f6-102">如何：向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="dc8f6-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="dc8f6-103">尽管 Visual Studio 中的 Windows 窗体设计器已优化为承载 Windows 窗体控件，但你也可以将 ActiveX 控件置于 Windows 窗体上。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="dc8f6-104">向其中添加 ActiveX 控件时，Windows 窗体存在性能限制。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="dc8f6-105">向窗体添加 ActiveX 控件之前，必须将它们添加到 "工具箱"。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="dc8f6-106">有关详细信息，请参阅[COM 组件 "自定义工具箱" 对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="dc8f6-107">向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="dc8f6-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="dc8f6-108">若要向 Windows 窗体添加 ActiveX 控件，请双击工具箱中的控件。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="dc8f6-109">Visual Studio 会在项目中添加对该控件的所有引用。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="dc8f6-110">有关在 Windows 窗体上使用 ActiveX 控件时要记住的事项的详细信息，请参阅[在 Windows 窗体上承载 Activex 控件时的注意事项](considerations-when-hosting-an-activex-control-on-a-windows-form.md)。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dc8f6-111">Windows 窗体 ActiveX 控件导入程序（Aximp.exe）在导入 ActiveX 动态链接库时创建不同类型的事件参数。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="dc8f6-112">Aximp.exe 创建的参数类似于以下内容： `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`时，应使用 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="dc8f6-113">请注意，此 irregularity 不会阻止代码正常运行。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="dc8f6-114">有关详细信息，请参阅[Windows 窗体 ActiveX 控件导入程序（aximp.exe）](../../tools/aximp-exe-windows-forms-activex-control-importer.md)。</span><span class="sxs-lookup"><span data-stu-id="dc8f6-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc8f6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc8f6-115">See also</span></span>

- [<span data-ttu-id="dc8f6-116">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="dc8f6-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="dc8f6-117">[不同语言和库中的控件和可编程对象的比较](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dc8f6-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="dc8f6-118">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="dc8f6-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="dc8f6-119">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="dc8f6-119">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="dc8f6-120">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="dc8f6-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="dc8f6-121">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="dc8f6-121">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
