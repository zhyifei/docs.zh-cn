---
title: "Windows 窗体中的更加安全的打印"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f36ee150e4dcca74141b644a55451abd4a4fd21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="more-secure-printing-in-windows-forms"></a>Windows 窗体中的更加安全的打印
Windows 窗体应用程序经常包含打印功能。 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]使用<xref:System.Drawing.Printing.PrintingPermission>类控制对打印功能的访问，关联<xref:System.Drawing.Printing.PrintingPermissionLevel>枚举值以指示的访问级别。 默认情况下，在本地 Intranet 和 Internet 区域中; 默认情况下启用打印但是，在这两个区域受到限制的访问级别。 是否可以打印你的应用程序，需要用户交互或不能打印取决于授予应用程序的权限值。 默认情况下，本地 Intranet 区域接收<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>访问和 Intranet 区域接收<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>访问。  
  
 下表显示可在每个打印的权限级别的功能。  
  
|PrintingPermissionLevel|描述|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|提供对所有已安装的打印机的完全访问权限。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|允许以编程方式打印到默认打印机和更安全的打印通过限制性打印对话框。 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting> 的子集。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|仅从更多限制的对话框中提供打印。 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 的子集。|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|禁止对打印机的访问。 <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 的子集。|  
  
## <a name="see-also"></a>请参阅  
 [在 Windows 窗体中提高文件和数据访问的安全性](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [Windows 窗体中额外的安全注意事项](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [Windows 窗体中的安全性概述](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Windows 窗体安全](../../../docs/framework/winforms/windows-forms-security.md)
