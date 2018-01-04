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
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="dd073-102">Windows 窗体中的更加安全的打印</span><span class="sxs-lookup"><span data-stu-id="dd073-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="dd073-103">Windows 窗体应用程序经常包含打印功能。</span><span class="sxs-lookup"><span data-stu-id="dd073-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="dd073-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]使用<xref:System.Drawing.Printing.PrintingPermission>类控制对打印功能的访问，关联<xref:System.Drawing.Printing.PrintingPermissionLevel>枚举值以指示的访问级别。</span><span class="sxs-lookup"><span data-stu-id="dd073-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="dd073-105">默认情况下，在本地 Intranet 和 Internet 区域中; 默认情况下启用打印但是，在这两个区域受到限制的访问级别。</span><span class="sxs-lookup"><span data-stu-id="dd073-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="dd073-106">是否可以打印你的应用程序，需要用户交互或不能打印取决于授予应用程序的权限值。</span><span class="sxs-lookup"><span data-stu-id="dd073-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="dd073-107">默认情况下，本地 Intranet 区域接收<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>访问和 Intranet 区域接收<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>访问。</span><span class="sxs-lookup"><span data-stu-id="dd073-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="dd073-108">下表显示可在每个打印的权限级别的功能。</span><span class="sxs-lookup"><span data-stu-id="dd073-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="dd073-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="dd073-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="dd073-110">描述</span><span class="sxs-lookup"><span data-stu-id="dd073-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="dd073-111">提供对所有已安装的打印机的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="dd073-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="dd073-112">允许以编程方式打印到默认打印机和更安全的打印通过限制性打印对话框。</span><span class="sxs-lookup"><span data-stu-id="dd073-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="dd073-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting> 的子集。</span><span class="sxs-lookup"><span data-stu-id="dd073-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="dd073-114">仅从更多限制的对话框中提供打印。</span><span class="sxs-lookup"><span data-stu-id="dd073-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="dd073-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> 的子集。</span><span class="sxs-lookup"><span data-stu-id="dd073-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="dd073-116">禁止对打印机的访问。</span><span class="sxs-lookup"><span data-stu-id="dd073-116">Prevents access to printers.</span></span> <span data-ttu-id="dd073-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> 是 <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> 的子集。</span><span class="sxs-lookup"><span data-stu-id="dd073-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd073-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd073-118">See Also</span></span>  
 [<span data-ttu-id="dd073-119">在 Windows 窗体中提高文件和数据访问的安全性</span><span class="sxs-lookup"><span data-stu-id="dd073-119">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [<span data-ttu-id="dd073-120">Windows 窗体中额外的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="dd073-120">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="dd073-121">Windows 窗体中的安全性概述</span><span class="sxs-lookup"><span data-stu-id="dd073-121">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="dd073-122">Windows 窗体安全</span><span class="sxs-lookup"><span data-stu-id="dd073-122">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)
