---
title: 部署引用 Power Pack 控件 (Visual Studio) 的应用程序
ms.date: 07/20/2015
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
ms.openlocfilehash: 3fd46a6e8aad61d2f8ce5a230c856470f913d0bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551769"
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="0c467-102">部署引用 Power Pack 控件 (Visual Studio) 的应用程序</span><span class="sxs-lookup"><span data-stu-id="0c467-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="0c467-103">如果你想要部署引用 Power Pack 控件的应用程序 (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>， <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>， <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>，或<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>)，必须在目标计算机上安装控件。</span><span class="sxs-lookup"><span data-stu-id="0c467-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="0c467-104">安装必备组件 Power Pack 控件</span><span class="sxs-lookup"><span data-stu-id="0c467-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="0c467-105">若要成功部署应用程序，你还必须部署应用程序引用的所有组件。</span><span class="sxs-lookup"><span data-stu-id="0c467-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="0c467-106">安装必备组件的过程称为 *引导*。</span><span class="sxs-lookup"><span data-stu-id="0c467-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="0c467-107">在开发计算机上安装 Visual Studio 时，Power Pack 引导程序包添加到 Visual Studio 引导程序目录。</span><span class="sxs-lookup"><span data-stu-id="0c467-107">When Visual Studio is installed on your development computer, a Power Packs bootstrapper package is added to the Visual Studio bootstrapper directory.</span></span> <span data-ttu-id="0c467-108">按照添加 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 或 Windows 安装程序部署必备项的过程进行操作时即可使用此包。</span><span class="sxs-lookup"><span data-stu-id="0c467-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="0c467-109">默认情况下，引导组件将从与安装包的相同的位置进行部署。</span><span class="sxs-lookup"><span data-stu-id="0c467-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="0c467-110">或者，你可以选择从 URL 或文件共享位置部署组件，用户可从这些位置按需进行下载。</span><span class="sxs-lookup"><span data-stu-id="0c467-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c467-111">若要安装引导组件，用户可能需要对计算机的管理员或类似用户权限。</span><span class="sxs-lookup"><span data-stu-id="0c467-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="0c467-112">对于 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 应用程序，这意味着无论应用程序所指定的安全级别是什么，用户都需要管理员权限才能安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c467-112">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="0c467-113">安装应用程序后，用户无需管理员权限即可运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c467-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="0c467-114">在安装期间，将提示用户如果它们不存在于目标计算机上安装 Power Pack 控件。</span><span class="sxs-lookup"><span data-stu-id="0c467-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="0c467-115">作为引导的替代方法，你可以预先部署 Power Pack 控件，通过使用诸如 Microsoft Systems Management Server 之类的电子软件分发系统。</span><span class="sxs-lookup"><span data-stu-id="0c467-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c467-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c467-116">See also</span></span>
- [<span data-ttu-id="0c467-117">如何：将系统必备与 ClickOnce 应用程序一起安装</span><span class="sxs-lookup"><span data-stu-id="0c467-117">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)
- [<span data-ttu-id="0c467-118">Visual Basic Power Pack 控件</span><span class="sxs-lookup"><span data-stu-id="0c467-118">Visual Basic Power Packs Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
