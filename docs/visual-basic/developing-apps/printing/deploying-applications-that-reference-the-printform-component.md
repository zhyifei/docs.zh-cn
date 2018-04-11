---
title: 部署引用 PrintForm 组件 (Visual Basic 中) 的应用程序
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 15b6e21e769c90e23e66e4f87b37f74462423985
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a><span data-ttu-id="f29d0-102">部署引用 PrintForm 组件 (Visual Basic 中) 的应用程序</span><span class="sxs-lookup"><span data-stu-id="f29d0-102">Deploying applications that reference the PrintForm component (Visual Basic)</span></span>
<span data-ttu-id="f29d0-103">如果你想要部署引用 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件的应用程序，则必须在目标计算机上安装该组件。</span><span class="sxs-lookup"><span data-stu-id="f29d0-103">If you want to deploy an application that references the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component, the component must be installed on the destination computer.</span></span>  
  
 <span data-ttu-id="f29d0-104">Visual Studio 中不再包含 PowerPack 控件，但你可以从 [下载中心](http://www.microsoft.com/en-us/download/details.aspx?id=25169)下载它们。</span><span class="sxs-lookup"><span data-stu-id="f29d0-104">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
## <a name="installing-the-printform-as-a-prerequisite"></a><span data-ttu-id="f29d0-105">将 PrintForm 安装为必备项</span><span class="sxs-lookup"><span data-stu-id="f29d0-105">Installing the PrintForm as a prerequisite</span></span>  
 <span data-ttu-id="f29d0-106">若要成功部署应用程序，你还必须部署应用程序引用的所有组件。</span><span class="sxs-lookup"><span data-stu-id="f29d0-106">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="f29d0-107">安装必备组件的过程称为 *引导*。</span><span class="sxs-lookup"><span data-stu-id="f29d0-107">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="f29d0-108">在开发计算机上安装 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件时，会将 Microsoft Visual Basic Power Pack 引导程序包添加到 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 引导程序目录。</span><span class="sxs-lookup"><span data-stu-id="f29d0-108">When the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is installed on your development computer, a Microsoft Visual Basic Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] bootstrapper directory.</span></span> <span data-ttu-id="f29d0-109">按照添加 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 或 Windows 安装程序部署必备项的过程进行操作时即可使用此包。</span><span class="sxs-lookup"><span data-stu-id="f29d0-109">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="f29d0-110">默认情况下，引导组件将从与安装包的相同的位置进行部署。</span><span class="sxs-lookup"><span data-stu-id="f29d0-110">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="f29d0-111">或者，你可以选择从 URL 或文件共享位置部署组件，用户可从这些位置按需进行下载。</span><span class="sxs-lookup"><span data-stu-id="f29d0-111">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f29d0-112">若要安装引导组件，用户可能需要对计算机的管理员或类似用户权限。</span><span class="sxs-lookup"><span data-stu-id="f29d0-112">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="f29d0-113">对于 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 应用程序，这意味着无论应用程序所指定的安全级别是什么，用户都需要管理员权限才能安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="f29d0-113">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="f29d0-114">安装应用程序后，用户无需管理员权限即可运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="f29d0-114">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="f29d0-115">在安装期间，如果目标计算机上没有 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件，系统将提示用户进行安装。</span><span class="sxs-lookup"><span data-stu-id="f29d0-115">During installation, users will be prompted to install the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component if it is not present on the destination computer.</span></span>  
  
 <span data-ttu-id="f29d0-116">作为引导的替代方法，你可以使用电子软件分发系统（如 Microsoft Systems Management Server）预先部署 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件。</span><span class="sxs-lookup"><span data-stu-id="f29d0-116">As an alternative to bootstrapping, you can pre-deploy the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component by using an electronic software distribution system like Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29d0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f29d0-117">See also</span></span>  
 [<span data-ttu-id="f29d0-118">如何：与 ClickOnce 应用程序一起安装系统必备组件</span><span class="sxs-lookup"><span data-stu-id="f29d0-118">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="f29d0-119">PrintForm 组件</span><span class="sxs-lookup"><span data-stu-id="f29d0-119">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
