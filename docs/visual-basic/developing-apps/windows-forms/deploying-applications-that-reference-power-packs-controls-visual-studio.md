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
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>部署引用 Power Pack 控件 (Visual Studio) 的应用程序
如果你想要部署引用 Power Pack 控件的应用程序 (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>， <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>， <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>，或<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>)，必须在目标计算机上安装控件。  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>安装必备组件 Power Pack 控件  
 若要成功部署应用程序，你还必须部署应用程序引用的所有组件。 安装必备组件的过程称为 *引导*。  
  
 在开发计算机上安装 Visual Studio 时，Power Pack 引导程序包添加到 Visual Studio 引导程序目录。 按照添加 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 或 Windows 安装程序部署必备项的过程进行操作时即可使用此包。  
  
 默认情况下，引导组件将从与安装包的相同的位置进行部署。 或者，你可以选择从 URL 或文件共享位置部署组件，用户可从这些位置按需进行下载。  
  
> [!NOTE]
>  若要安装引导组件，用户可能需要对计算机的管理员或类似用户权限。 对于 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 应用程序，这意味着无论应用程序所指定的安全级别是什么，用户都需要管理员权限才能安装该应用程序。 安装应用程序后，用户无需管理员权限即可运行该应用程序。  
  
 在安装期间，将提示用户如果它们不存在于目标计算机上安装 Power Pack 控件。  
  
 作为引导的替代方法，你可以预先部署 Power Pack 控件，通过使用诸如 Microsoft Systems Management Server 之类的电子软件分发系统。  
  
## <a name="see-also"></a>请参阅
- [如何：将系统必备与 ClickOnce 应用程序一起安装](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)
- [Visual Basic Power Pack 控件](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
