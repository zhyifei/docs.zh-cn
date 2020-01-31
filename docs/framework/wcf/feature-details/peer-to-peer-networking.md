---
title: 피어 투 피어 네트워킹
ms.date: 03/30/2017
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
ms.openlocfilehash: 2905a429e907f7e97c482c22229a6bc928c52243
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744669"
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="c6de1-102">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="c6de1-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="c6de1-103">对等通道是 Windows Communication Foundation （WCF）中的一种多方对等（P2P）通信技术。</span><span class="sxs-lookup"><span data-stu-id="c6de1-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="c6de1-104">피어 채널은 애플리케이션 개발자에게 안전하고 확장 가능한 메시지 기반 P2P 통신 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6de1-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="c6de1-105">피어 채널을 활용할 수 있는 다자간 애플리케이션의 대표적인 예로 여러 사용자가 서버 없이 피어 투 피어 방식으로 서로 채트하는 대화방 같은 협업 애플리케이션을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6de1-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="c6de1-106">피어 채널은 소비자 및 기업 시나리오 모두에서 P2P 협업, 콘텐츠 배포, 부하 분산 및 분산 처리를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6de1-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="c6de1-107">默认情况下，在 Windows Vista 上启用对等通道，这与 WCF 完全相同。</span><span class="sxs-lookup"><span data-stu-id="c6de1-107">Peer Channel is enabled by default on Windows Vista, as is all of WCF.</span></span> <span data-ttu-id="c6de1-108">피어 채널 클래스에 액세스하려면 프로젝트에 System.ServiceModel.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6de1-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="c6de1-109">다음 단원에는 피어 투 피어 네트워킹에 대한 정보와 피어 채널 클래스를 사용하여 피어가 활성화된 네트워크 애플리케이션을 만드는 데 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6de1-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6de1-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c6de1-110">In This Section</span></span>  
 <span data-ttu-id="c6de1-111">[对等通道方案](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md)：介绍对等通道 api 支持的开发方案，如发布/订阅消息传递、协作、分布式处理和游戏。</span><span class="sxs-lookup"><span data-stu-id="c6de1-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="c6de1-112">[对等通道概念](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)：介绍对等网格、对等节点、对等通道安全和对等解析程序。</span><span class="sxs-lookup"><span data-stu-id="c6de1-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="c6de1-113">[生成对等通道应用程序](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)：提供有关开发对等通道应用程序的指导。</span><span class="sxs-lookup"><span data-stu-id="c6de1-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="c6de1-114">피어 채널 코드 예제</span><span class="sxs-lookup"><span data-stu-id="c6de1-114">Peer Channel Code Examples</span></span>  
 <span data-ttu-id="c6de1-115">[对等通道自定义对等解析程序](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c6de1-115">[Peer Channel Custom Peer Resolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span></span>  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="c6de1-116">피어 채널 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="c6de1-116">Peer Channel Team blog</span></span>  
 [<span data-ttu-id="c6de1-117">对等通道团队博客</span><span class="sxs-lookup"><span data-stu-id="c6de1-117">Peer Channel Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/peerchan/)
