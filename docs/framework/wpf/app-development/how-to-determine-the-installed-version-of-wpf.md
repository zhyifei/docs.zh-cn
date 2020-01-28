---
title: 确定安装的 WPF 版本
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: 8fc5c380779891b44b7c4f7f8aeb5ed119d8b768
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735692"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>如何：确定安装的 WPF 的版本
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 的当前已安装版本的版本号位于**注册表**中。  
  
 查找版本号：  
  
1. 在“开始” 菜单上，单击“运行”。  
  
2. 在 "**打开**" 中，键入**regedit.exe**。  
  
3. 打开以下项：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 版本号存储在 "**版本**" 值中。
