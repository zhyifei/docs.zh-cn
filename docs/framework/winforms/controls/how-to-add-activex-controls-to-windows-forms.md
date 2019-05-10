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
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="bba2d-102">如何：向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="bba2d-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="bba2d-103">虽然 Visual Studio 中的 Windows 窗体设计器已经过优化，承载 Windows 窗体控件，还可以将 Windows 窗体上的 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="bba2d-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="bba2d-104">ActiveX 控件添加到它们时，有有关 Windows 窗体的性能限制。</span><span class="sxs-lookup"><span data-stu-id="bba2d-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="bba2d-105">向窗体添加 ActiveX 控件之前，必须将它们添加到工具箱。</span><span class="sxs-lookup"><span data-stu-id="bba2d-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="bba2d-106">有关详细信息，请参阅[COM 组件、 自定义工具箱对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="bba2d-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="bba2d-107">向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="bba2d-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="bba2d-108">若要向 Windows 窗体添加 ActiveX 控件，请双击工具箱上的控件。</span><span class="sxs-lookup"><span data-stu-id="bba2d-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="bba2d-109">Visual Studio 项目中添加对该控件的所有引用。</span><span class="sxs-lookup"><span data-stu-id="bba2d-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="bba2d-110">使用 Windows 窗体上的 ActiveX 控件时，需要注意的事项的详细信息，请参阅[承载 Windows 窗体上的 ActiveX 控件时的注意事项](considerations-when-hosting-an-activex-control-on-a-windows-form.md)。</span><span class="sxs-lookup"><span data-stu-id="bba2d-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bba2d-111">Windows 窗体 ActiveX 控件导入程序 (AxImp.exe) 比预期的 ActiveX 动态链接库导入后创建其他类型的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bba2d-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="bba2d-112">AxImp.exe 所创建的参数，如下所示： `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`，当`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`预期。</span><span class="sxs-lookup"><span data-stu-id="bba2d-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="bba2d-113">请注意，此不一致情况不会阻止代码工作正常。</span><span class="sxs-lookup"><span data-stu-id="bba2d-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="bba2d-114">有关详细信息，请参阅[Windows 窗体 ActiveX 控件导入程序 (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)。</span><span class="sxs-lookup"><span data-stu-id="bba2d-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bba2d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bba2d-115">See also</span></span>

- [<span data-ttu-id="bba2d-116">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="bba2d-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="bba2d-117">[不同语言和库中的控件和可编程对象的比较](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bba2d-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="bba2d-118">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="bba2d-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="bba2d-119">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="bba2d-119">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="bba2d-120">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="bba2d-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="bba2d-121">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="bba2d-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="bba2d-122">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="bba2d-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
