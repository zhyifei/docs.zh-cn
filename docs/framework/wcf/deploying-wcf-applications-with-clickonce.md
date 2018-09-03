---
title: 使用 ClickOnce 部署 WCF 应用程序
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: d733c6f523393737418c6394707c1d4e6e9c1710
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467454"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="edea7-102">使用 ClickOnce 部署 WCF 应用程序</span><span class="sxs-lookup"><span data-stu-id="edea7-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="edea7-103">使用 Windows Communication Foundation (WCF) 的客户端应用程序可以使用 ClickOnce 技术进行部署。</span><span class="sxs-lookup"><span data-stu-id="edea7-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="edea7-104">只要客户端应用程序已使用受信任的证书进行数据签名，此技术就允许它们充分利用代码访问安全机制所提供的运行时安全保护。</span><span class="sxs-lookup"><span data-stu-id="edea7-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="edea7-105">用于对 ClickOnce 应用程序签名的证书必须位于受信任的发行者存储中，并且必须将客户端计算机上的本地安全策略配置为对使用该发行者的证书签名的应用程序授予完全信任权限。</span><span class="sxs-lookup"><span data-stu-id="edea7-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="edea7-106">有关配置 ClickOnce 应用程序和受信任的发行者的信息，请参阅[配置 ClickOnce 受信任的发布者](https://go.microsoft.com/fwlink/?LinkId=94774)。</span><span class="sxs-lookup"><span data-stu-id="edea7-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edea7-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="edea7-107">See Also</span></span>  
 [<span data-ttu-id="edea7-108">受信任的应用程序部署概述</span><span class="sxs-lookup"><span data-stu-id="edea7-108">Trusted Application Deployment Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="edea7-109">ClickOnce 部署的 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="edea7-109">ClickOnce Deployment for Windows Forms Applications</span></span>](https://go.microsoft.com/fwlink/?LinkId=94776)
