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
ms.openlocfilehash: 154953680426f98a9506feb0b8f4de25c873b795
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959677"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>如何：取消文件对话框自动升级
在应用程序中使用 <xref:System.Windows.Forms.OpenFileDialog> 和 <xref:System.Windows.Forms.SaveFileDialog> 类时，其外观和行为取决于运行应用程序的 Windows 的版本。 在 Windows Vista 上显示在 .NET Framework 2.0 或更早版本上创建的应用程序时，<xref:System.Windows.Forms.OpenFileDialog> 和 <xref:System.Windows.Forms.SaveFileDialog> 会自动显示 Windows Vista 外观和行为。 从 .NET Framework 3.0 开始，你可以选择退出自动升级，以使用 Windows XP 样式的外观和行为显示 <xref:System.Windows.Forms.OpenFileDialog> 和 <xref:System.Windows.Forms.SaveFileDialog>。  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>取消文件对话框自动升级  
  
1. 在显示对话框之前，将 <xref:System.Windows.Forms.OpenFileDialog> 或 <xref:System.Windows.Forms.SaveFileDialog> 的 <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 属性设置为 "`false`"。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FileDialog>
