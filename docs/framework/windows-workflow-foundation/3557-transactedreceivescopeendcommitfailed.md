---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ea57cc60f9626763308267a98624c825f8312b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="981ec-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="981ec-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="981ec-103">属性</span><span class="sxs-lookup"><span data-stu-id="981ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="981ec-104">ID</span><span class="sxs-lookup"><span data-stu-id="981ec-104">ID</span></span>|<span data-ttu-id="981ec-105">3557</span><span class="sxs-lookup"><span data-stu-id="981ec-105">3557</span></span>|  
|<span data-ttu-id="981ec-106">关键字</span><span class="sxs-lookup"><span data-stu-id="981ec-106">Keywords</span></span>|<span data-ttu-id="981ec-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="981ec-107">WFServices</span></span>|  
|<span data-ttu-id="981ec-108">级别</span><span class="sxs-lookup"><span data-stu-id="981ec-108">Level</span></span>|<span data-ttu-id="981ec-109">信息</span><span class="sxs-lookup"><span data-stu-id="981ec-109">Information</span></span>|  
|<span data-ttu-id="981ec-110">通道</span><span class="sxs-lookup"><span data-stu-id="981ec-110">Channel</span></span>|<span data-ttu-id="981ec-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="981ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="981ec-112">描述</span><span class="sxs-lookup"><span data-stu-id="981ec-112">Description</span></span>  
 <span data-ttu-id="981ec-113">指示对 CommittableTransaction 上的 EndCommit 的调用引发 TransactionException。</span><span class="sxs-lookup"><span data-stu-id="981ec-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="981ec-114">消息</span><span class="sxs-lookup"><span data-stu-id="981ec-114">Message</span></span>  
 <span data-ttu-id="981ec-115">ID 为“%1”的 CommittableTransaction 上的 EndCommit 调用引发了具有以下消息的 TransactionException:“%2”。</span><span class="sxs-lookup"><span data-stu-id="981ec-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="981ec-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="981ec-116">Details</span></span>  
  
|<span data-ttu-id="981ec-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="981ec-117">Data Item Name</span></span>|<span data-ttu-id="981ec-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="981ec-118">Data Item Type</span></span>|<span data-ttu-id="981ec-119">描述</span><span class="sxs-lookup"><span data-stu-id="981ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="981ec-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="981ec-120">TransactionId</span></span>|<span data-ttu-id="981ec-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="981ec-121">xs:string</span></span>|<span data-ttu-id="981ec-122">CommittableTransaction 的 ID。</span><span class="sxs-lookup"><span data-stu-id="981ec-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="981ec-123">例外</span><span class="sxs-lookup"><span data-stu-id="981ec-123">Exception</span></span>|<span data-ttu-id="981ec-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="981ec-124">xs:string</span></span>|<span data-ttu-id="981ec-125">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="981ec-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="981ec-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="981ec-126">AppDomain</span></span>|<span data-ttu-id="981ec-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="981ec-127">xs:string</span></span>|<span data-ttu-id="981ec-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="981ec-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
