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
ms.openlocfilehash: bbde260cc7f05226c9b06325b45708e1cde3cf8c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976885"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>如何：取消文件对话框自动升级
在应用程序中使用 <xref:System.Windows.Forms.OpenFileDialog> 和 <xref:System.Windows.Forms.SaveFileDialog> 类时，其外观和行为取决于运行应用程序的 Windows 的版本。 在 Windows Vista 上显示在 .NET Framework 2.0 或更早版本上创建的应用程序时，<xref:System.Windows.Forms.OpenFileDialog> 和 <xref:System.Windows.Forms.SaveFileDialog> 会自动显示 Windows Vista 外观和行为。 从 .NET Framework 3.0 开始，可以选择退出自动升级，以显示 <xref:System.Windows.Forms.OpenFileDialog> 并 <xref:System.Windows.Forms.SaveFileDialog> [!INCLUDE[winxp](../../../../includes/winxp-md.md)]样式的外观和行为。  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>取消文件对话框自动升级  
  
1. 在显示对话框之前，将 <xref:System.Windows.Forms.OpenFileDialog> 或 <xref:System.Windows.Forms.SaveFileDialog> 的 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 属性设置为 "`false`"。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.FileDialog>
