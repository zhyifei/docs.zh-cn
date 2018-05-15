---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="625fb-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="625fb-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="625fb-103">属性</span><span class="sxs-lookup"><span data-stu-id="625fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="625fb-104">ID</span><span class="sxs-lookup"><span data-stu-id="625fb-104">ID</span></span>|<span data-ttu-id="625fb-105">3552</span><span class="sxs-lookup"><span data-stu-id="625fb-105">3552</span></span>|  
|<span data-ttu-id="625fb-106">关键字</span><span class="sxs-lookup"><span data-stu-id="625fb-106">Keywords</span></span>|<span data-ttu-id="625fb-107">配额、WFServices</span><span class="sxs-lookup"><span data-stu-id="625fb-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="625fb-108">级别</span><span class="sxs-lookup"><span data-stu-id="625fb-108">Level</span></span>|<span data-ttu-id="625fb-109">警告</span><span class="sxs-lookup"><span data-stu-id="625fb-109">Warning</span></span>|  
|<span data-ttu-id="625fb-110">通道</span><span class="sxs-lookup"><span data-stu-id="625fb-110">Channel</span></span>|<span data-ttu-id="625fb-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="625fb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="625fb-112">描述</span><span class="sxs-lookup"><span data-stu-id="625fb-112">Description</span></span>  
 <span data-ttu-id="625fb-113">指示达到了中止值“MaxPendingMessagesPerChannel”。</span><span class="sxs-lookup"><span data-stu-id="625fb-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="625fb-114">消息</span><span class="sxs-lookup"><span data-stu-id="625fb-114">Message</span></span>  
 <span data-ttu-id="625fb-115">已达到了中止值 maxpendingmessagesperchannel 的"%1"。</span><span class="sxs-lookup"><span data-stu-id="625fb-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="625fb-116">若要增加此限制，请调整 BufferedReceiveServiceBehavior 中的 MaxPendingMessagesPerChannel 属性。</span><span class="sxs-lookup"><span data-stu-id="625fb-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="625fb-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="625fb-117">Details</span></span>  
  
|<span data-ttu-id="625fb-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="625fb-118">Data Item Name</span></span>|<span data-ttu-id="625fb-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="625fb-119">Data Item Type</span></span>|<span data-ttu-id="625fb-120">描述</span><span class="sxs-lookup"><span data-stu-id="625fb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="625fb-121">限制值</span><span class="sxs-lookup"><span data-stu-id="625fb-121">Limit</span></span>|<span data-ttu-id="625fb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="625fb-122">xs:string</span></span>|<span data-ttu-id="625fb-123">中止值 MaxPendingMessagesPerChannel。</span><span class="sxs-lookup"><span data-stu-id="625fb-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="625fb-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="625fb-124">AppDomain</span></span>|<span data-ttu-id="625fb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="625fb-125">xs:string</span></span>|<span data-ttu-id="625fb-126">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="625fb-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
