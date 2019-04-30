---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945933"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="5b5ee-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="5b5ee-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="5b5ee-103">属性</span><span class="sxs-lookup"><span data-stu-id="5b5ee-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b5ee-104">Id</span><span class="sxs-lookup"><span data-stu-id="5b5ee-104">ID</span></span>|<span data-ttu-id="5b5ee-105">3552</span><span class="sxs-lookup"><span data-stu-id="5b5ee-105">3552</span></span>|  
|<span data-ttu-id="5b5ee-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5b5ee-106">Keywords</span></span>|<span data-ttu-id="5b5ee-107">配额、WFServices</span><span class="sxs-lookup"><span data-stu-id="5b5ee-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="5b5ee-108">级别</span><span class="sxs-lookup"><span data-stu-id="5b5ee-108">Level</span></span>|<span data-ttu-id="5b5ee-109">警告</span><span class="sxs-lookup"><span data-stu-id="5b5ee-109">Warning</span></span>|  
|<span data-ttu-id="5b5ee-110">通道</span><span class="sxs-lookup"><span data-stu-id="5b5ee-110">Channel</span></span>|<span data-ttu-id="5b5ee-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="5b5ee-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b5ee-112">描述</span><span class="sxs-lookup"><span data-stu-id="5b5ee-112">Description</span></span>  
 <span data-ttu-id="5b5ee-113">指示达到了中止值“MaxPendingMessagesPerChannel”。</span><span class="sxs-lookup"><span data-stu-id="5b5ee-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b5ee-114">消息</span><span class="sxs-lookup"><span data-stu-id="5b5ee-114">Message</span></span>  
 <span data-ttu-id="5b5ee-115">已命中的中止值 maxpendingmessagesperchannel 的"%1"。</span><span class="sxs-lookup"><span data-stu-id="5b5ee-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="5b5ee-116">若要增加此限制，请调整 BufferedReceiveServiceBehavior 中的 MaxPendingMessagesPerChannel 属性。</span><span class="sxs-lookup"><span data-stu-id="5b5ee-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b5ee-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b5ee-117">Details</span></span>  
  
|<span data-ttu-id="5b5ee-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5b5ee-118">Data Item Name</span></span>|<span data-ttu-id="5b5ee-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5b5ee-119">Data Item Type</span></span>|<span data-ttu-id="5b5ee-120">描述</span><span class="sxs-lookup"><span data-stu-id="5b5ee-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b5ee-121">限制值</span><span class="sxs-lookup"><span data-stu-id="5b5ee-121">Limit</span></span>|<span data-ttu-id="5b5ee-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b5ee-122">xs:string</span></span>|<span data-ttu-id="5b5ee-123">中止值 MaxPendingMessagesPerChannel。</span><span class="sxs-lookup"><span data-stu-id="5b5ee-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="5b5ee-124">应用程序域</span><span class="sxs-lookup"><span data-stu-id="5b5ee-124">AppDomain</span></span>|<span data-ttu-id="5b5ee-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b5ee-125">xs:string</span></span>|<span data-ttu-id="5b5ee-126">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5b5ee-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
