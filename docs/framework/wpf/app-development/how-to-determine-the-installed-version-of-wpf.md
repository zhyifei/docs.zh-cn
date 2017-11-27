---
title: "如何：确定安装的 WPF 的版本"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60f2dd65702a5dfcff4cbafa97e5a48080b8e5be
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>如何：确定安装的 WPF 的版本
当前安装的版本的版本号[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]位于**注册表**。  
  
 若要查找的版本号：  
  
1.  在“开始”  菜单上，单击“运行” 。  
  
2.  在**打开**，类型**regedit.exe**。  
  
3.  打开以下项：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]版本号存储在**版本**值。
