---
title: 4207 - MaximumRetriesExceededForSqlCommand
ms.date: 03/30/2017
ms.assetid: 8c8bee26-9ad4-4e01-bd16-0e1fd510fb6b
ms.openlocfilehash: b763e087d8ead2bcc0fadd1d0223ae1bd58c9fd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511454"
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a><span data-ttu-id="6636b-102">4207 - MaximumRetriesExceededForSqlCommand</span><span class="sxs-lookup"><span data-stu-id="6636b-102">4207 - MaximumRetriesExceededForSqlCommand</span></span>
## <a name="properties"></a><span data-ttu-id="6636b-103">属性</span><span class="sxs-lookup"><span data-stu-id="6636b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6636b-104">ID</span><span class="sxs-lookup"><span data-stu-id="6636b-104">ID</span></span>|<span data-ttu-id="6636b-105">4207</span><span class="sxs-lookup"><span data-stu-id="6636b-105">4207</span></span>|  
|<span data-ttu-id="6636b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="6636b-106">Keywords</span></span>|<span data-ttu-id="6636b-107">配额，FInstanceStore</span><span class="sxs-lookup"><span data-stu-id="6636b-107">Quota, WFInstanceStore</span></span>|  
|<span data-ttu-id="6636b-108">级别</span><span class="sxs-lookup"><span data-stu-id="6636b-108">Level</span></span>|<span data-ttu-id="6636b-109">信息</span><span class="sxs-lookup"><span data-stu-id="6636b-109">Information</span></span>|  
|<span data-ttu-id="6636b-110">通道</span><span class="sxs-lookup"><span data-stu-id="6636b-110">Channel</span></span>|<span data-ttu-id="6636b-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="6636b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6636b-112">描述</span><span class="sxs-lookup"><span data-stu-id="6636b-112">Description</span></span>  
 <span data-ttu-id="6636b-113">指示 SQL 提供程序正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="6636b-113">Indicates SQL provider is giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6636b-114">消息</span><span class="sxs-lookup"><span data-stu-id="6636b-114">Message</span></span>  
 <span data-ttu-id="6636b-115">正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="6636b-115">Giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6636b-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="6636b-116">Details</span></span>  
  
|<span data-ttu-id="6636b-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="6636b-117">Data Item Name</span></span>|<span data-ttu-id="6636b-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="6636b-118">Data Item Type</span></span>|<span data-ttu-id="6636b-119">描述</span><span class="sxs-lookup"><span data-stu-id="6636b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6636b-120">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6636b-120">AppDomain</span></span>|<span data-ttu-id="6636b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6636b-121">xs:string</span></span>|<span data-ttu-id="6636b-122">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="6636b-122">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
