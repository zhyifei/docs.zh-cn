---
title: 安全性
description: 构建适用于 Azure 的云本机 .NET 应用 |安全
ms.date: 05/13/2020
ms.openlocfilehash: 9afbc2c960fdd16721e1d3aa7fd01d5c0c1fe2f9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613663"
---
# <a name="security"></a><span data-ttu-id="20dad-103">安全性</span><span class="sxs-lookup"><span data-stu-id="20dad-103">Security</span></span>

<span data-ttu-id="20dad-104">这不是一天，这种情况下，新闻不会包含有关公司遭受黑客攻击或失去其客户数据的某些故事。</span><span class="sxs-lookup"><span data-stu-id="20dad-104">Not a day goes by where the news doesn't contain some story about a company being hacked or somehow losing their customers' data.</span></span> <span data-ttu-id="20dad-105">即使是国家/地区，也不会受到将安全性视为事后的问题所造成的问题。</span><span class="sxs-lookup"><span data-stu-id="20dad-105">Even countries aren't immune to the problems created by treating security as an afterthought.</span></span> <span data-ttu-id="20dad-106">多年来，公司已经处理了客户数据的安全问题，事实上，他们的整个网络都是 "良好"。</span><span class="sxs-lookup"><span data-stu-id="20dad-106">For years, companies have treated the security of customer data and, in fact, their entire networks as something of a "nice to have".</span></span> <span data-ttu-id="20dad-107">Windows server 仍处于未修补状态，古版本的 PHP 保持运行状态，并且 MongoDB 数据库在世界各地保持宽。</span><span class="sxs-lookup"><span data-stu-id="20dad-107">Windows servers were left unpatched, ancient versions of PHP kept running and MongoDB databases left wide open to the world.</span></span>

<span data-ttu-id="20dad-108">但是，在生成和部署应用程序时，可能会有实际的影响，而不是保持安全思维。</span><span class="sxs-lookup"><span data-stu-id="20dad-108">However, there are starting to be real-world consequences for not maintaining a security mindset when building and deploying applications.</span></span> <span data-ttu-id="20dad-109">很多公司都在[NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/)的2017爆发期间未对服务器和台式机进行修补时，对服务器和台式机进行修补会出现什么情况。</span><span class="sxs-lookup"><span data-stu-id="20dad-109">Many companies learned the hard way what can happen when servers and desktops aren't patched during the 2017 outbreak of [NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/).</span></span> <span data-ttu-id="20dad-110">这些攻击的成本很容易进入数十亿，其中有一些估算将此类攻击的损失降低了10000000000美元。</span><span class="sxs-lookup"><span data-stu-id="20dad-110">The cost of these attacks has easily reached into the billions, with some estimates putting the losses from this single attack at 10 billion US dollars.</span></span>

<span data-ttu-id="20dad-111">即使政府也不会受到黑客攻击。</span><span class="sxs-lookup"><span data-stu-id="20dad-111">Even governments aren't immune to hacking incidents.</span></span> <span data-ttu-id="20dad-112">巴尔的摩的城市已 ransom，这使得公民无法支付[自己的帐单](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers)或使用市县服务。</span><span class="sxs-lookup"><span data-stu-id="20dad-112">The city of Baltimore was held ransom by [criminals](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers) making it impossible for citizens to pay their bills or use city services.</span></span>

<span data-ttu-id="20dad-113">还规定了对个人数据进行某些数据保护的法规提升。</span><span class="sxs-lookup"><span data-stu-id="20dad-113">There has also been an increase in legislation that mandates certain data protections for personal data.</span></span> <span data-ttu-id="20dad-114">在欧洲，GDPR 已在超过一年的时间内有效，并且加利福尼亚州最近的用户通过其自己的版本 CCDA，这将于2020年1月1日生效。</span><span class="sxs-lookup"><span data-stu-id="20dad-114">In Europe, GDPR has been in effect for more than a year and, more recently, California passed their own version called CCDA, which comes into effect January 1, 2020.</span></span> <span data-ttu-id="20dad-115">GDPR 下的罚款可能会导致公司不会成为企业。</span><span class="sxs-lookup"><span data-stu-id="20dad-115">The fines under GDPR can be so punishing as to put companies out of business.</span></span> <span data-ttu-id="20dad-116">Google 已经罚款50000000欧元用于违规，但这只是与潜在罚款相比，存储桶中的一个下降。</span><span class="sxs-lookup"><span data-stu-id="20dad-116">Google has already been fined 50 million Euros for violations, but that's just a drop in the bucket compared with the potential fines.</span></span>

<span data-ttu-id="20dad-117">简而言之，安全性是严重的业务。</span><span class="sxs-lookup"><span data-stu-id="20dad-117">In short, security is serious business.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="20dad-118">[上一页](identity-server.md)
>[下一页](azure-security.md)</span><span class="sxs-lookup"><span data-stu-id="20dad-118">[Previous](identity-server.md)
[Next](azure-security.md)</span></span>
