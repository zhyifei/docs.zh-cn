---
title: 如何：向 Windows 窗体添加 ActiveX 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: c851a215638e60642bf93564f4884b5a79d430d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="8eff5-102">如何：向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="8eff5-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="8eff5-103">虽然 Windows 窗体设计器已经过优化，主机 Windows 窗体控件，您还可将 Windows 窗体上的 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="8eff5-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8eff5-104">ActiveX 控件添加到它们时，有一些 Windows 窗体的性能限制。</span><span class="sxs-lookup"><span data-stu-id="8eff5-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="8eff5-105">在向窗体添加 ActiveX 控件之前，必须将它们添加到工具箱中。</span><span class="sxs-lookup"><span data-stu-id="8eff5-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="8eff5-106">有关详细信息，请参阅[COM 组件、 自定义工具箱对话框](http://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c)。</span><span class="sxs-lookup"><span data-stu-id="8eff5-106">For more information, see [COM Components, Customize Toolbox Dialog Box](http://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8eff5-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="8eff5-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8eff5-108">若要更改设置，请单击 **“工具”** 菜单上的 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="8eff5-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8eff5-109">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="8eff5-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="8eff5-110">若要向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="8eff5-110">To add an ActiveX control to your Windows Form</span></span>  
  
-   <span data-ttu-id="8eff5-111">双击工具箱上的控件。</span><span class="sxs-lookup"><span data-stu-id="8eff5-111">Double-click the control on the Toolbox.</span></span>  
  
     <span data-ttu-id="8eff5-112">Visual Studio 项目中添加到控件的所有引用。</span><span class="sxs-lookup"><span data-stu-id="8eff5-112">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="8eff5-113">使用 Windows 窗体上的 ActiveX 控件时，需要注意的事项的详细信息，请参阅[承载 Windows 窗体上的 ActiveX 控件时的注意事项](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md)。</span><span class="sxs-lookup"><span data-stu-id="8eff5-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8eff5-114">Windows 窗体 ActiveX 控件导入程序 (AxImp.exe) 创建不同类型的事件自变量比预期时 ActiveX 动态链接库中导入。</span><span class="sxs-lookup"><span data-stu-id="8eff5-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="8eff5-115">AxImp.exe 所创建的自变量是类似于以下： `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`，当`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`预期。</span><span class="sxs-lookup"><span data-stu-id="8eff5-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="8eff5-116">请注意，此不一致情况不会阻止代码工作正常。</span><span class="sxs-lookup"><span data-stu-id="8eff5-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="8eff5-117">有关详细信息，请参阅[Windows 窗体 ActiveX 控件导入程序 (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)。</span><span class="sxs-lookup"><span data-stu-id="8eff5-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eff5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8eff5-118">See Also</span></span>  
 [<span data-ttu-id="8eff5-119">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="8eff5-119">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="8eff5-120">不同语言和库中的控件和可编程对象的比较</span><span class="sxs-lookup"><span data-stu-id="8eff5-120">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="8eff5-121">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="8eff5-121">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="8eff5-122">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="8eff5-122">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="8eff5-123">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="8eff5-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="8eff5-124">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="8eff5-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="8eff5-125">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="8eff5-125">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
