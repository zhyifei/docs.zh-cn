---
title: 使用 ClickOnce 部署 WCF 应用程序
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: d733c6f523393737418c6394707c1d4e6e9c1710
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222209"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>使用 ClickOnce 部署 WCF 应用程序
使用 Windows Communication Foundation (WCF) 的客户端应用程序可以使用 ClickOnce 技术进行部署。 只要客户端应用程序已使用受信任的证书进行数据签名，此技术就允许它们充分利用代码访问安全机制所提供的运行时安全保护。 用于对 ClickOnce 应用程序签名的证书必须位于受信任的发行者存储中，并且必须将客户端计算机上的本地安全策略配置为对使用该发行者的证书签名的应用程序授予完全信任权限。  
  
 有关配置 ClickOnce 应用程序和受信任的发行者的信息，请参阅[配置 ClickOnce 受信任的发布者](https://go.microsoft.com/fwlink/?LinkId=94774)。  
  
## <a name="see-also"></a>请参阅  
 [受信任的应用程序部署概述](https://go.microsoft.com/fwlink/?LinkId=94775)  
 [ClickOnce 部署的 Windows 窗体应用程序](https://go.microsoft.com/fwlink/?LinkId=94776)
