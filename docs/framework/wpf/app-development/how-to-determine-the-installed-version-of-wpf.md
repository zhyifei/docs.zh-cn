---
title: 如何：确定已安装的 WPF 版本
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768015"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="59630-102">如何：确定已安装的 WPF 版本</span><span class="sxs-lookup"><span data-stu-id="59630-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="59630-103">当前安装的版本的版本号[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]位于**注册表**。</span><span class="sxs-lookup"><span data-stu-id="59630-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="59630-104">若要查找的版本号：</span><span class="sxs-lookup"><span data-stu-id="59630-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="59630-105">在“开始”  菜单上，单击“运行” 。</span><span class="sxs-lookup"><span data-stu-id="59630-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="59630-106">在中**开放**，类型**regedit.exe**。</span><span class="sxs-lookup"><span data-stu-id="59630-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="59630-107">打开以下项：</span><span class="sxs-lookup"><span data-stu-id="59630-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="59630-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版本号存储在**版本**值。</span><span class="sxs-lookup"><span data-stu-id="59630-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
