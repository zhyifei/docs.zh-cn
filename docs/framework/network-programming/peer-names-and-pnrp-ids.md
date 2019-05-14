---
title: 对等名称和 PNRP ID
ms.date: 03/30/2017
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
ms.openlocfilehash: 8cdd5151d029436d11c78806cf7673861cc0d8a4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623121"
---
# <a name="peer-names-and-pnrp-ids"></a><span data-ttu-id="7dce7-102">对等名称和 PNRP ID</span><span class="sxs-lookup"><span data-stu-id="7dce7-102">Peer Names and PNRP IDs</span></span>
<span data-ttu-id="7dce7-103">对等名称代表通信的终结点，可以是计算机、用户、组、服务或者任何与对等有关的、可以解析为 IPv6 地址的事物。</span><span class="sxs-lookup"><span data-stu-id="7dce7-103">A Peer Name represents an endpoint for communication, which can be a computer, a user, a group, a service, or anything associated with a Peer that can be resolved to an IPv6 address.</span></span> <span data-ttu-id="7dce7-104">对等名称解析协议 (PNRP) 将统计学上唯一的对等名称用于创建标识云成员的 PNRP ID。</span><span class="sxs-lookup"><span data-stu-id="7dce7-104">The Peer Name Resolution Protocol (PNRP) takes the statistically unique Peer Name for the creation of a PNRP ID, which is used to identify cloud members.</span></span>  
  
## <a name="peer-names"></a><span data-ttu-id="7dce7-105">对等名称</span><span class="sxs-lookup"><span data-stu-id="7dce7-105">Peer Names</span></span>  
 <span data-ttu-id="7dce7-106">对等名称可以注册成不安全的或安全的。</span><span class="sxs-lookup"><span data-stu-id="7dce7-106">Peer names can be registered as unsecured or secured.</span></span> <span data-ttu-id="7dce7-107">不安全名称是文本字符串，存在遭受欺骗的风险，因为任何人都可注册重复的不安全名称。</span><span class="sxs-lookup"><span data-stu-id="7dce7-107">Unsecured names are just text strings that are subject to spoofing, as anyone can register a duplicate unsecured name.</span></span> <span data-ttu-id="7dce7-108">不安全名称最适用于专用或受保护的网络。</span><span class="sxs-lookup"><span data-stu-id="7dce7-108">Unsecured names are best used in private or otherwise protected networks.</span></span> <span data-ttu-id="7dce7-109">安全名称受到证书和数字签名的保护。</span><span class="sxs-lookup"><span data-stu-id="7dce7-109">Secured names are protected with a certificate and a digital signature.</span></span> <span data-ttu-id="7dce7-110">只有原发布者才能证实自己拥有安全名称。</span><span class="sxs-lookup"><span data-stu-id="7dce7-110">Only the original publisher will be able to prove ownership of a secured name.</span></span>  
  
 <span data-ttu-id="7dce7-111">云和范围的组合为参与 PNRP 活动的对等方提供了相当安全的环境。</span><span class="sxs-lookup"><span data-stu-id="7dce7-111">The combination of cloud and scope provides a reasonably secure environment for peers that participate in PNRP activity.</span></span> <span data-ttu-id="7dce7-112">但使用安全对等名称并不能确保网络应用程序的整体安全性。</span><span class="sxs-lookup"><span data-stu-id="7dce7-112">However, using a secured peer name does not ensure the overall security of the networking application.</span></span> <span data-ttu-id="7dce7-113">应用程序的安全性是视具体实现而定的。</span><span class="sxs-lookup"><span data-stu-id="7dce7-113">Security of the application is implementation-dependent.</span></span>  
  
 <span data-ttu-id="7dce7-114">安全对等名称仅由其所有者注册，并使用公钥加密进行保护。</span><span class="sxs-lookup"><span data-stu-id="7dce7-114">Secured peer names are only registered by their owner and are protected with public key cryptography.</span></span> <span data-ttu-id="7dce7-115">安全对等名称被视为属于拥有相应私钥的对等实体。</span><span class="sxs-lookup"><span data-stu-id="7dce7-115">A secured peer name is considered owned by the peer entity having the corresponding private key.</span></span> <span data-ttu-id="7dce7-116">可以通过使用私钥签名的认证对等地址 (CPA) 验证所有权。</span><span class="sxs-lookup"><span data-stu-id="7dce7-116">Ownership can be proved via the certified peer address (CPA), which is signed using the private key.</span></span> <span data-ttu-id="7dce7-117">恶意用户没有相应的私钥，无法伪造对等名称的所有权。</span><span class="sxs-lookup"><span data-stu-id="7dce7-117">A malicious user cannot forge ownership of a peer name without the corresponding private key.</span></span>  
  
## <a name="pnrp-ids"></a><span data-ttu-id="7dce7-118">PNRP ID</span><span class="sxs-lookup"><span data-stu-id="7dce7-118">PNRP IDs</span></span>  
 <span data-ttu-id="7dce7-119">![PNRP ID](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")</span><span class="sxs-lookup"><span data-stu-id="7dce7-119">![PNRP ID](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")</span></span>  
  
 <span data-ttu-id="7dce7-120">PNRP ID 由以下内容组成：</span><span class="sxs-lookup"><span data-stu-id="7dce7-120">PNRP IDs are composed of the following:</span></span>  
  
- <span data-ttu-id="7dce7-121">高序位 128 位，也就是对等 (P2P) ID，是分配至终结点的对等名称的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="7dce7-121">The high-order 128 bits, known as the peer-to-peer (P2P) ID, are a hash of a peer name assigned to the endpoint.</span></span> <span data-ttu-id="7dce7-122">对等名称采用以下格式：*Authority.Classifier*。</span><span class="sxs-lookup"><span data-stu-id="7dce7-122">The peer name has the following format: *Authority.Classifier*.</span></span> <span data-ttu-id="7dce7-123">对于安全名称，Authority 是对等名称公钥的安全哈希算法 1 (SHA1) 的哈希代码，是十六进制字符。</span><span class="sxs-lookup"><span data-stu-id="7dce7-123">For secured names, *Authority* is the Secure Hash Algorithm 1 (SHA1) hash of the public key of the peer name in hexadecimal characters.</span></span> <span data-ttu-id="7dce7-124">对于不安全名称，Authority 为单字符“0”。</span><span class="sxs-lookup"><span data-stu-id="7dce7-124">For unsecured names, the *Authority* is the single character "0".</span></span> <span data-ttu-id="7dce7-125"> 是标识应用程序的字符串。</span><span class="sxs-lookup"><span data-stu-id="7dce7-125">*Classifier* is a string that identifies the application.</span></span> <span data-ttu-id="7dce7-126">对等名称 Classifier 最多长 149 个字符，包括 `null` 终止符在内。</span><span class="sxs-lookup"><span data-stu-id="7dce7-126">No peer name classifier can be greater than 149 characters long, including the `null` terminator.</span></span>  
  
- <span data-ttu-id="7dce7-127">低序位 128 位用于服务定位，它是标识同一云中同一 P2P ID 的不同实例的生成数字。</span><span class="sxs-lookup"><span data-stu-id="7dce7-127">The low-order 128 bits are used for the Service Location, which is a generated number that identifies different instances of the same P2P ID in the same cloud.</span></span>  
  
 <span data-ttu-id="7dce7-128">P2P ID 和服务定位的这种组合实现从一台计算机注册多个 PNRP ID。</span><span class="sxs-lookup"><span data-stu-id="7dce7-128">This combination of P2P ID and Service Location allows multiple PNRP IDs to be registered from a single computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dce7-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dce7-129">See also</span></span>

- <xref:System.Net.PeerToPeer.PeerName>
- <xref:System.Net.PeerToPeer>
