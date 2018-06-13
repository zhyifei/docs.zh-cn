---
title: 如何：确定安装的 WPF 的版本
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: c59fa0d0a4d94c6e6a2ab72a4cd7a3c066649fb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545846"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="ae857-102">如何：确定安装的 WPF 的版本</span><span class="sxs-lookup"><span data-stu-id="ae857-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="ae857-103">当前安装的版本的版本号[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]位于**注册表**。</span><span class="sxs-lookup"><span data-stu-id="ae857-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="ae857-104">若要查找的版本号：</span><span class="sxs-lookup"><span data-stu-id="ae857-104">To find the version number:</span></span>  
  
1.  <span data-ttu-id="ae857-105">在“开始”  菜单上，单击“运行” 。</span><span class="sxs-lookup"><span data-stu-id="ae857-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="ae857-106">在**打开**，类型**regedit.exe**。</span><span class="sxs-lookup"><span data-stu-id="ae857-106">In **Open**, type **regedit.exe**.</span></span>  
  
3.  <span data-ttu-id="ae857-107">打开以下项：</span><span class="sxs-lookup"><span data-stu-id="ae857-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="ae857-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版本号存储在**版本**值。</span><span class="sxs-lookup"><span data-stu-id="ae857-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
