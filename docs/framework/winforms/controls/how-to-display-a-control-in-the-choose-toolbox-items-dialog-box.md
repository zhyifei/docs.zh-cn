---
title: 如何：中显示控件选择工具箱项对话框
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 56dad16b7a0bd8f0e7423b4a70e7173578150cbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520446"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="0eb1c-102">如何：中显示控件选择工具箱项对话框</span><span class="sxs-lookup"><span data-stu-id="0eb1c-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="0eb1c-103">在开发和分发控件，您可能希望出现在这些控件**选择工具箱项**对话框中，右键单击时显示**工具箱**，然后选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="0eb1c-104">可以使控件能够显示在此对话框中的使用 AssemblyFoldersEx 注册过程。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="0eb1c-105">若要在选择工具箱项对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="0eb1c-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="0eb1c-106">在控件程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="0eb1c-107">有关详细信息，请参阅[如何：将程序集安装到全局程序集缓存](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="0eb1c-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="0eb1c-108">或</span><span class="sxs-lookup"><span data-stu-id="0eb1c-108">-or-</span></span>  
  
-   <span data-ttu-id="0eb1c-109">使用 AssemblyFoldersEx 注册过程中注册您的控件和其关联的设计时程序集。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="0eb1c-110">AssemblyFoldersEx 是框架的第三方供应商在其中存储每个版本，它们支持的路径的注册表位置。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="0eb1c-111">设计时间解析度可以查看在此注册表位置，以查找引用程序集。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="0eb1c-112">注册表脚本可以指定你想要显示在工具箱中的控件。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="0eb1c-113">有关详细信息，请参阅[部署自定义控件和设计时程序集 (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)。</span><span class="sxs-lookup"><span data-stu-id="0eb1c-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb1c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eb1c-114">See also</span></span>
- [<span data-ttu-id="0eb1c-115">“选择工具箱项”对话框 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="0eb1c-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)
- [<span data-ttu-id="0eb1c-116">部署自定义控件和设计时程序集 (Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="0eb1c-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)
- [<span data-ttu-id="0eb1c-117">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="0eb1c-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="0eb1c-118">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="0eb1c-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="0eb1c-119">演练：自动填充工具箱与自定义组件</span><span class="sxs-lookup"><span data-stu-id="0eb1c-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
