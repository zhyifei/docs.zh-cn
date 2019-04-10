---
title: Windows 窗体中的更加安全的打印
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 5ee170980ed02d90606c774e2a7055f047292e33
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197355"
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="51bba-102">Windows 窗体中的更加安全的打印</span><span class="sxs-lookup"><span data-stu-id="51bba-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="51bba-103">Windows 窗体应用程序通常包括打印功能。</span><span class="sxs-lookup"><span data-stu-id="51bba-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="51bba-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]使用<xref:System.Drawing.Printing.PrintingPermission>类控制对打印功能的访问，关联<xref:System.Drawing.Printing.PrintingPermissionLevel>枚举值，以指示的访问级别。</span><span class="sxs-lookup"><span data-stu-id="51bba-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="51bba-105">默认情况下，在本地 Intranet 和 Internet 区域中; 默认情况下启用打印但是，在这两个区域受到限制的访问级别。</span><span class="sxs-lookup"><span data-stu-id="51bba-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="51bba-106">是否可以打印您的应用程序，需要用户交互或不能打印取决于授予应用程序的权限值。</span><span class="sxs-lookup"><span data-stu-id="51bba-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="51bba-107">默认情况下，本地 Intranet 区域接收<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>访问权限和 Intranet 区域接收<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>访问。</span><span class="sxs-lookup"><span data-stu-id="51bba-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="51bba-108">下表显示了在每个打印的权限级别可用的功能。</span><span class="sxs-lookup"><span data-stu-id="51bba-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="51bba-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="51bba-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="51bba-110">描述</span><span class="sxs-lookup"><span data-stu-id="51bba-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="51bba-111">提供对所有已安装打印机的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="51bba-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="51bba-112">可以以编程方式打印到默认打印机和限制性的打印对话框通过更安全的打印。</span><span class="sxs-lookup"><span data-stu-id="51bba-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> <span data-ttu-id="51bba-113">是的子集<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>。</span><span class="sxs-lookup"><span data-stu-id="51bba-113">is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="51bba-114">仅从更多限制的对话框提供打印。</span><span class="sxs-lookup"><span data-stu-id="51bba-114">Provides printing only from a more-restricted dialog box.</span></span> <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> <span data-ttu-id="51bba-115">是的子集<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>。</span><span class="sxs-lookup"><span data-stu-id="51bba-115">is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="51bba-116">禁止对打印机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="51bba-116">Prevents access to printers.</span></span> <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> <span data-ttu-id="51bba-117">是的子集<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>。</span><span class="sxs-lookup"><span data-stu-id="51bba-117">is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51bba-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="51bba-118">See also</span></span>

- [<span data-ttu-id="51bba-119">Windows 窗体中更加安全的文件和数据访问</span><span class="sxs-lookup"><span data-stu-id="51bba-119">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)
- [<span data-ttu-id="51bba-120">Windows 窗体中额外的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="51bba-120">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="51bba-121">Windows 窗体中的安全性概述</span><span class="sxs-lookup"><span data-stu-id="51bba-121">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="51bba-122">Windows 窗体安全</span><span class="sxs-lookup"><span data-stu-id="51bba-122">Windows Forms Security</span></span>](windows-forms-security.md)
