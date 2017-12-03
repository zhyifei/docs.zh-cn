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
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="baf9d-102">使用 ClickOnce 部署 WCF 应用程序</span><span class="sxs-lookup"><span data-stu-id="baf9d-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="baf9d-103">可以采用 ClickOnce 技术部署使用 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="baf9d-103">Client applications using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="baf9d-104">只要客户端应用程序已使用受信任的证书进行数据签名，此技术就允许它们充分利用代码访问安全机制所提供的运行时安全保护。</span><span class="sxs-lookup"><span data-stu-id="baf9d-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="baf9d-105">用于对 ClickOnce 应用程序签名的证书必须位于受信任的发行者存储中，并且必须将客户端计算机上的本地安全策略配置为对使用该发行者的证书签名的应用程序授予完全信任权限。</span><span class="sxs-lookup"><span data-stu-id="baf9d-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="baf9d-106">配置 ClickOnce 应用程序和受信任的发行者信息，请参阅[配置 ClickOnce 受信任的发行者](http://go.microsoft.com/fwlink/?LinkId=94774)。</span><span class="sxs-lookup"><span data-stu-id="baf9d-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf9d-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="baf9d-107">See Also</span></span>  
 [<span data-ttu-id="baf9d-108">受信任的应用程序部署概述</span><span class="sxs-lookup"><span data-stu-id="baf9d-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="baf9d-109">ClickOnce 部署适用于 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="baf9d-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)
