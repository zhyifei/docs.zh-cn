---
title: 如何：在“选择工具箱项”对话框中显示控件
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 4ed3f6ffdf8a86d050b81311c9211767d8b179b8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623601"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="b3ec6-102">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="b3ec6-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="b3ec6-103">在开发和分发控件，您可能希望出现在这些控件**选择工具箱项**对话框中，右键单击时显示**工具箱**，然后选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="b3ec6-104">可以使控件能够显示在此对话框中的使用 AssemblyFoldersEx 注册过程。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="b3ec6-105">若要在选择工具箱项对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="b3ec6-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
- <span data-ttu-id="b3ec6-106">在控件程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="b3ec6-107">有关详细信息，请参阅[如何：将程序集安装到全局程序集缓存](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="b3ec6-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="b3ec6-108">或</span><span class="sxs-lookup"><span data-stu-id="b3ec6-108">-or-</span></span>  
  
- <span data-ttu-id="b3ec6-109">使用 AssemblyFoldersEx 注册过程中注册您的控件和其关联的设计时程序集。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="b3ec6-110">AssemblyFoldersEx 是框架的第三方供应商在其中存储每个版本，它们支持的路径的注册表位置。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="b3ec6-111">设计时间解析度可以查看在此注册表位置，以查找引用程序集。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="b3ec6-112">注册表脚本可以指定你想要显示在工具箱中的控件。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="b3ec6-113">有关详细信息，请参阅[部署自定义控件和设计时程序集](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="b3ec6-113">For more information, see [Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ec6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3ec6-114">See also</span></span>

- <span data-ttu-id="b3ec6-115">[“选择工具箱项”对话框 (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b3ec6-115">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- <span data-ttu-id="b3ec6-116">[部署自定义控件和设计时程序集](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b3ec6-116">[Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span></span>
- [<span data-ttu-id="b3ec6-117">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="b3ec6-117">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="b3ec6-118">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="b3ec6-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="b3ec6-119">演练：自动填充工具箱与自定义组件</span><span class="sxs-lookup"><span data-stu-id="b3ec6-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
