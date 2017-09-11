---
title: "部署引用 PrintForm 组件 (Visual Basic 中) 的应用程序 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b625e0c58653f1ee9a2d263d7d2d29ad3b2e3c1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="014d8-102">部署引用 PrintForm 组件 (Visual Basic 中) 的应用程序</span><span class="sxs-lookup"><span data-stu-id="014d8-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="014d8-103">如果你想要部署的应用程序引用<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>组件，必须在目标计算机上安装的组件。</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="014d8-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="014d8-104">Visual Studio 中不再包含 PowerPack 控件，但你可以从 [下载中心](http://www.microsoft.com/en-us/download/details.aspx?id=25169)下载它们。</span><span class="sxs-lookup"><span data-stu-id="014d8-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="014d8-105">作为系统必备组件安装 PrintForm</span><span class="sxs-lookup"><span data-stu-id="014d8-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="014d8-106">若要成功部署应用程序，你还必须部署应用程序引用的所有组件。</span><span class="sxs-lookup"><span data-stu-id="014d8-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="014d8-107">安装必备项的过程称为 *引导*。</span><span class="sxs-lookup"><span data-stu-id="014d8-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="014d8-108">当<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>在开发计算机上安装组件，Microsoft Visual Basic Power Packs 引导程序包添加到[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]引导程序目录。</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="014d8-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="014d8-109">当您按照添加对于任何系统必备组件的过程时，该包就可[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]或 Windows Installer 部署。</span><span class="sxs-lookup"><span data-stu-id="014d8-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="014d8-110">默认情况下，引导组件将从与安装包的相同的位置进行部署。</span><span class="sxs-lookup"><span data-stu-id="014d8-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="014d8-111">或者，你可以选择从 URL 或文件共享位置部署组件，用户可从这些位置按需进行下载。</span><span class="sxs-lookup"><span data-stu-id="014d8-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="014d8-112">若要安装引导组件，用户可能需要对计算机的管理员或类似用户权限。</span><span class="sxs-lookup"><span data-stu-id="014d8-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="014d8-113">有关[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]应用程序，这意味着，用户需要管理权限才能安装应用程序，而不考虑应用程序所指定的安全级别。</span><span class="sxs-lookup"><span data-stu-id="014d8-113">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="014d8-114">安装应用程序后，用户无需管理员权限即可运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="014d8-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="014d8-115">在安装期间，将提示用户安装<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>是否不存在于目标计算机上的组件。</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="014d8-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="014d8-116">作为引导的替代方法，您可以预先部署<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>组件通过使用电子软件分发系统，如 Microsoft Systems Management Server。</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm></span><span class="sxs-lookup"><span data-stu-id="014d8-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014d8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="014d8-117">See also</span></span>  
 <span data-ttu-id="014d8-118">[如何︰ 与 ClickOnce 应用程序一起安装系统必备组件](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="014d8-118">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="014d8-119"> [PrintForm 组件](../../../visual-basic/developing-apps/printing/printform-component.md)</span><span class="sxs-lookup"><span data-stu-id="014d8-119"> [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)</span></span>
