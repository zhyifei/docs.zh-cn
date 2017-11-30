---
title: "如何：在“选择工具箱项”对话框中显示控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f7bbb13e8a2b877d0f503e091b5bb8b1e7e89d00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="8f9c0-102">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="8f9c0-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="8f9c0-103">在开发和分发控件，您可能希望显示在这些控件**选择工具箱项**对话框中，右键单击时显示**工具箱**和选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="8f9c0-104">你可以启用控件，以显示在此对话框中，通过使用 AssemblyFoldersEx 注册过程。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="8f9c0-105">若要在选择工具箱项对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="8f9c0-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="8f9c0-106">控件程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="8f9c0-107">有关详细信息，请参阅[如何： 将程序集安装到全局程序集缓存](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="8f9c0-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="8f9c0-108">- 或 -</span><span class="sxs-lookup"><span data-stu-id="8f9c0-108">-or-</span></span>  
  
-   <span data-ttu-id="8f9c0-109">通过使用 AssemblyFoldersEx 注册过程中注册你的控件和其关联的设计时程序集。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="8f9c0-110">AssemblyFoldersEx 是框架的第三方供应商在其中存储每个版本，它们支持的路径的注册表位置。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="8f9c0-111">设计时解析可以查看在此注册表位置来查找引用程序集。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="8f9c0-112">注册表脚本可以指定你想要显示在工具箱中的控件。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="8f9c0-113">有关详细信息，请参阅[部署自定义控件和设计时程序集 (Visual Studio 2013)](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)。</span><span class="sxs-lookup"><span data-stu-id="8f9c0-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9c0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f9c0-114">See Also</span></span>  
 [<span data-ttu-id="8f9c0-115">“选择工具箱项”对话框 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8f9c0-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="8f9c0-116">部署自定义控件和设计时程序集 (Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="8f9c0-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [<span data-ttu-id="8f9c0-117">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="8f9c0-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="8f9c0-118">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="8f9c0-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="8f9c0-119">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="8f9c0-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
