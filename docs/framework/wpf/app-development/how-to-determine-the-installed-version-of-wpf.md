---
title: 如何：确定已安装的 WPF 版本
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052451"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="f2763-102">如何：确定已安装的 WPF 版本</span><span class="sxs-lookup"><span data-stu-id="f2763-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="f2763-103">当前安装的版本的版本号[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]位于**注册表**。</span><span class="sxs-lookup"><span data-stu-id="f2763-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="f2763-104">若要查找的版本号：</span><span class="sxs-lookup"><span data-stu-id="f2763-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="f2763-105">在“开始”  菜单上，单击“运行” 。</span><span class="sxs-lookup"><span data-stu-id="f2763-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="f2763-106">在中**开放**，类型**regedit.exe**。</span><span class="sxs-lookup"><span data-stu-id="f2763-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="f2763-107">打开以下项：</span><span class="sxs-lookup"><span data-stu-id="f2763-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="f2763-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版本号存储在**版本**值。</span><span class="sxs-lookup"><span data-stu-id="f2763-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
