---
title: 部署引用 PrintForm 组件 (Visual Basic 中) 的应用程序
ms.date: 07/20/2015
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
ms.openlocfilehash: 78d332c88b45fa9b1204d9d5352a6027409254e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562422"
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>部署引用 PrintForm 组件 (Visual Basic 中) 的应用程序
如果你想要部署引用 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件的应用程序，则必须在目标计算机上安装该组件。  
  
 Visual Studio 中不再包含 PowerPack 控件，但你可以从 [下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=25169)下载它们。  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>将 PrintForm 安装为必备项  
 若要成功部署应用程序，你还必须部署应用程序引用的所有组件。 安装必备组件的过程称为 *引导*。  
  
 当<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>在开发计算机上安装组件，Microsoft Visual Basic Power Pack 引导程序包添加到 Visual Studio 引导程序目录。 按照添加 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 或 Windows 安装程序部署必备项的过程进行操作时即可使用此包。  
  
 默认情况下，引导组件将从与安装包的相同的位置进行部署。 或者，你可以选择从 URL 或文件共享位置部署组件，用户可从这些位置按需进行下载。  
  
> [!NOTE]
>  若要安装引导组件，用户可能需要对计算机的管理员或类似用户权限。 对于 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 应用程序，这意味着无论应用程序所指定的安全级别是什么，用户都需要管理员权限才能安装该应用程序。 安装应用程序后，用户无需管理员权限即可运行该应用程序。  
  
 在安装期间，如果目标计算机上没有 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件，系统将提示用户进行安装。  
  
 作为引导的替代方法，你可以使用电子软件分发系统（如 Microsoft Systems Management Server）预先部署 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件。  
  
## <a name="see-also"></a>请参阅
- [如何：将系统必备与 ClickOnce 应用程序一起安装](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)
- [PrintForm 组件](../../../visual-basic/developing-apps/printing/printform-component.md)
