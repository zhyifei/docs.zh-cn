---
title: "使用 ClickOnce 部署 WCF 应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 714e8341c58e5337d8e45bf61b48137d33fa51b9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a>使用 ClickOnce 部署 WCF 应用程序
可以采用 ClickOnce 技术部署使用 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 的客户端应用程序。 只要客户端应用程序已使用受信任的证书进行数据签名，此技术就允许它们充分利用代码访问安全机制所提供的运行时安全保护。 用于对 ClickOnce 应用程序签名的证书必须位于受信任的发行者存储中，并且必须将客户端计算机上的本地安全策略配置为对使用该发行者的证书签名的应用程序授予完全信任权限。  
  
 配置 ClickOnce 应用程序和受信任的发行者信息，请参阅[配置 ClickOnce 受信任的发行者](http://go.microsoft.com/fwlink/?LinkId=94774)。  
  
## <a name="see-also"></a>另请参阅  
 [受信任的应用程序部署概述](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [ClickOnce 部署适用于 Windows 窗体应用程序](http://go.microsoft.com/fwlink/?LinkId=94776)
