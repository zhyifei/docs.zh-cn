---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eabc6a6915560d8c49e695d5d681f1544689cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="d9e59-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="d9e59-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="d9e59-103">属性</span><span class="sxs-lookup"><span data-stu-id="d9e59-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9e59-104">ID</span><span class="sxs-lookup"><span data-stu-id="d9e59-104">ID</span></span>|<span data-ttu-id="d9e59-105">3550</span><span class="sxs-lookup"><span data-stu-id="d9e59-105">3550</span></span>|  
|<span data-ttu-id="d9e59-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d9e59-106">Keywords</span></span>|<span data-ttu-id="d9e59-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d9e59-107">WFServices</span></span>|  
|<span data-ttu-id="d9e59-108">级别</span><span class="sxs-lookup"><span data-stu-id="d9e59-108">Level</span></span>|<span data-ttu-id="d9e59-109">信息</span><span class="sxs-lookup"><span data-stu-id="d9e59-109">Information</span></span>|  
|<span data-ttu-id="d9e59-110">通道</span><span class="sxs-lookup"><span data-stu-id="d9e59-110">Channel</span></span>|<span data-ttu-id="d9e59-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="d9e59-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d9e59-112">描述</span><span class="sxs-lookup"><span data-stu-id="d9e59-112">Description</span></span>  
 <span data-ttu-id="d9e59-113">指示缓冲接收已失败。</span><span class="sxs-lookup"><span data-stu-id="d9e59-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="d9e59-114">服务实例准备好处理此特定操作时，将再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="d9e59-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d9e59-115">消息</span><span class="sxs-lookup"><span data-stu-id="d9e59-115">Message</span></span>  
 <span data-ttu-id="d9e59-116">此时不能执行操作“%1”。</span><span class="sxs-lookup"><span data-stu-id="d9e59-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="d9e59-117">服务实例准备好处理此特定操作时，将进行另一个尝试。</span><span class="sxs-lookup"><span data-stu-id="d9e59-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d9e59-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="d9e59-118">Details</span></span>  
  
|<span data-ttu-id="d9e59-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d9e59-119">Data Item Name</span></span>|<span data-ttu-id="d9e59-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d9e59-120">Data Item Type</span></span>|<span data-ttu-id="d9e59-121">描述</span><span class="sxs-lookup"><span data-stu-id="d9e59-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d9e59-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="d9e59-122">OperationName</span></span>|<span data-ttu-id="d9e59-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9e59-123">xs:string</span></span>|<span data-ttu-id="d9e59-124">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="d9e59-124">The name of the operation.</span></span>|  
|<span data-ttu-id="d9e59-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d9e59-125">AppDomain</span></span>|<span data-ttu-id="d9e59-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9e59-126">xs:string</span></span>|<span data-ttu-id="d9e59-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e59-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
