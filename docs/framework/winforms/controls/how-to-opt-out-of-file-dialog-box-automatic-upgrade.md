---
title: 如何：取消文件对话框自动升级
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 6fd34e1127747739423f6402f128194a3a39f5e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089141"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="47a06-102">如何：取消文件对话框自动升级</span><span class="sxs-lookup"><span data-stu-id="47a06-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="47a06-103">当<xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>在应用程序中使用类，其外观和行为取决于 Windows 运行应用程序的版本。</span><span class="sxs-lookup"><span data-stu-id="47a06-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="47a06-104">应用程序在创建时[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]或之前显示在[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]，<xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>自动显示与[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]外观和行为。</span><span class="sxs-lookup"><span data-stu-id="47a06-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="47a06-105">在中启动[!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)]，可以选择退出自动升级，以显示<xref:System.Windows.Forms.OpenFileDialog>并<xref:System.Windows.Forms.SaveFileDialog>与[!INCLUDE[winxp](../../../../includes/winxp-md.md)]-风格的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="47a06-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="47a06-106">取消文件对话框自动升级</span><span class="sxs-lookup"><span data-stu-id="47a06-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="47a06-107">设置<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>的属性<xref:System.Windows.Forms.OpenFileDialog>或<xref:System.Windows.Forms.SaveFileDialog>到`false`显示对话框之前。</span><span class="sxs-lookup"><span data-stu-id="47a06-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a06-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="47a06-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
