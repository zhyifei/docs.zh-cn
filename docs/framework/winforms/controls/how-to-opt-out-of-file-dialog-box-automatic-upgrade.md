---
title: "如何：取消文件对话框自动升级"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01be9e29c00f39125c8ee645242e986fac178ba2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>如何：取消文件对话框自动升级
当<xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>应用程序中使用类，其外观和行为依赖于的 Windows 运行应用程序的版本。 应用程序已在创建时[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]或更早版本上将显示[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]，<xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>自动显示与[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)]外观和行为。 从开始[!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)]，你可以选择取消自动升级，以显示<xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>与[!INCLUDE[winxp](../../../../includes/winxp-md.md)]-样式的外观和行为。  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>取消文件对话框自动升级  
  
1.  设置<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>属性<xref:System.Windows.Forms.OpenFileDialog>或<xref:System.Windows.Forms.SaveFileDialog>到`false`显示对话框之前。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.FileDialog>
