---
title: "部署引用 Power Pack 控件 (Visual Studio) 的应用程序 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ad1aba4f2e725abbe560f0c71fbb543e15741200
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="fabf8-102">部署引用 Power Pack 控件 (Visual Studio) 的应用程序</span><span class="sxs-lookup"><span data-stu-id="fabf8-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="fabf8-103">如果想要部署引用 Power Pack 控件的应用程序 (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>， <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>， <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>，或<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>)，必须在目标计算机上安装控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> </xref:Microsoft.VisualBasic.PowerPacks.OvalShape> </xref:Microsoft.VisualBasic.PowerPacks.LineShape></span><span class="sxs-lookup"><span data-stu-id="fabf8-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="fabf8-104">作为系统必备组件安装 Power Pack 控件</span><span class="sxs-lookup"><span data-stu-id="fabf8-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="fabf8-105">若要成功部署应用程序，你还必须部署应用程序引用的所有组件。</span><span class="sxs-lookup"><span data-stu-id="fabf8-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="fabf8-106">安装必备项的过程称为 *引导*。</span><span class="sxs-lookup"><span data-stu-id="fabf8-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="fabf8-107">当[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]安装到开发计算机上，引导程序包添加到一个 Power Pack[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]引导程序目录。</span><span class="sxs-lookup"><span data-stu-id="fabf8-107">When [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] is installed on your development computer, a Power Packs bootstrapper package is added to the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] bootstrapper directory.</span></span> <span data-ttu-id="fabf8-108">当您按照添加对于任何系统必备组件的过程时，该包就可[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]或 Windows Installer 部署。</span><span class="sxs-lookup"><span data-stu-id="fabf8-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="fabf8-109">默认情况下，引导组件将从与安装包的相同的位置进行部署。</span><span class="sxs-lookup"><span data-stu-id="fabf8-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="fabf8-110">或者，你可以选择从 URL 或文件共享位置部署组件，用户可从这些位置按需进行下载。</span><span class="sxs-lookup"><span data-stu-id="fabf8-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fabf8-111">若要安装引导组件，用户可能需要对计算机的管理员或类似用户权限。</span><span class="sxs-lookup"><span data-stu-id="fabf8-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="fabf8-112">有关[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]应用程序，这意味着，用户需要管理权限才能安装应用程序，而不考虑应用程序所指定的安全级别。</span><span class="sxs-lookup"><span data-stu-id="fabf8-112">For [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="fabf8-113">安装应用程序后，用户无需管理员权限即可运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fabf8-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="fabf8-114">在安装期间，将提示用户如果不存在于目标计算机上安装 Power Pack 控件。</span><span class="sxs-lookup"><span data-stu-id="fabf8-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="fabf8-115">作为引导的替代方法，你可以预先部署 Power Pack 控件，通过使用诸如 Microsoft Systems Management Server 的电子软件分发系统。</span><span class="sxs-lookup"><span data-stu-id="fabf8-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabf8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fabf8-116">See also</span></span>  
 <span data-ttu-id="fabf8-117">[如何︰ 与 ClickOnce 应用程序一起安装系统必备组件](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span><span class="sxs-lookup"><span data-stu-id="fabf8-117">[How to: Install Prerequisites with a ClickOnce Application](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5) </span></span>  
<span data-ttu-id="fabf8-118"> [Visual Basic Power Pack 控件](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span><span class="sxs-lookup"><span data-stu-id="fabf8-118"> [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)</span></span>
