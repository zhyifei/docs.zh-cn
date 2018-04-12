---
title: 部署引用 Power Pack 控件 (Visual Studio) 的应用程序
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2a9562acf05cd27eed7bc1ad963845af9a7ca5f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="be774-102">部署引用 Power Pack 控件 (Visual Studio) 的应用程序</span><span class="sxs-lookup"><span data-stu-id="be774-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="be774-103">如果你想要部署引用 Power Pack 控件的应用程序 (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>， <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>， <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>，或<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>)，必须在目标计算机上安装的控件。</span><span class="sxs-lookup"><span data-stu-id="be774-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="be774-104">作为必备组件安装 Power Pack 控件</span><span class="sxs-lookup"><span data-stu-id="be774-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="be774-105">若要成功部署应用程序，你还必须部署应用程序引用的所有组件。</span><span class="sxs-lookup"><span data-stu-id="be774-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="be774-106">安装必备组件的过程称为 *引导*。</span><span class="sxs-lookup"><span data-stu-id="be774-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="be774-107">当[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]安装在开发计算机，一个 Power Pack 引导程序包添加到上[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]引导程序目录。</span><span class="sxs-lookup"><span data-stu-id="be774-107">When [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] bootstrapper directory.</span></span> <span data-ttu-id="be774-108">按照添加 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 或 Windows 安装程序部署必备项的过程进行操作时即可使用此包。</span><span class="sxs-lookup"><span data-stu-id="be774-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="be774-109">默认情况下，引导组件将从与安装包的相同的位置进行部署。</span><span class="sxs-lookup"><span data-stu-id="be774-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="be774-110">或者，你可以选择从 URL 或文件共享位置部署组件，用户可从这些位置按需进行下载。</span><span class="sxs-lookup"><span data-stu-id="be774-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be774-111">若要安装引导组件，用户可能需要对计算机的管理员或类似用户权限。</span><span class="sxs-lookup"><span data-stu-id="be774-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="be774-112">对于 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 应用程序，这意味着无论应用程序所指定的安全级别是什么，用户都需要管理员权限才能安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="be774-112">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="be774-113">安装应用程序后，用户无需管理员权限即可运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="be774-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="be774-114">在安装期间，将提示用户，如果它们不存在于目标计算机上安装 Power Pack 控件。</span><span class="sxs-lookup"><span data-stu-id="be774-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="be774-115">作为引导的替代方法，你可以预先部署 Power Pack 控件，通过使用如 Microsoft Systems Management Server 的电子软件分发系统。</span><span class="sxs-lookup"><span data-stu-id="be774-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be774-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="be774-116">See also</span></span>  
 [<span data-ttu-id="be774-117">如何：与 ClickOnce 应用程序一起安装系统必备组件</span><span class="sxs-lookup"><span data-stu-id="be774-117">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="be774-118">Visual Basic Power Pack 控件</span><span class="sxs-lookup"><span data-stu-id="be774-118">Visual Basic Power Packs Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
