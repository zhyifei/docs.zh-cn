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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1f9f1066f1948411d584a2dee1af2129aa3a103
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="d56f4-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="d56f4-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="d56f4-103">属性</span><span class="sxs-lookup"><span data-stu-id="d56f4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d56f4-104">ID</span><span class="sxs-lookup"><span data-stu-id="d56f4-104">ID</span></span>|<span data-ttu-id="d56f4-105">3557</span><span class="sxs-lookup"><span data-stu-id="d56f4-105">3557</span></span>|  
|<span data-ttu-id="d56f4-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d56f4-106">Keywords</span></span>|<span data-ttu-id="d56f4-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d56f4-107">WFServices</span></span>|  
|<span data-ttu-id="d56f4-108">级别</span><span class="sxs-lookup"><span data-stu-id="d56f4-108">Level</span></span>|<span data-ttu-id="d56f4-109">信息</span><span class="sxs-lookup"><span data-stu-id="d56f4-109">Information</span></span>|  
|<span data-ttu-id="d56f4-110">通道</span><span class="sxs-lookup"><span data-stu-id="d56f4-110">Channel</span></span>|<span data-ttu-id="d56f4-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="d56f4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d56f4-112">描述</span><span class="sxs-lookup"><span data-stu-id="d56f4-112">Description</span></span>  
 <span data-ttu-id="d56f4-113">指示对 CommittableTransaction 上的 EndCommit 的调用引发 TransactionException。</span><span class="sxs-lookup"><span data-stu-id="d56f4-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d56f4-114">消息</span><span class="sxs-lookup"><span data-stu-id="d56f4-114">Message</span></span>  
 <span data-ttu-id="d56f4-115">ID 为“%1”的 CommittableTransaction 上的 EndCommit 调用引发了具有以下消息的 TransactionException:“%2”。</span><span class="sxs-lookup"><span data-stu-id="d56f4-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d56f4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d56f4-116">Details</span></span>  
  
|<span data-ttu-id="d56f4-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d56f4-117">Data Item Name</span></span>|<span data-ttu-id="d56f4-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d56f4-118">Data Item Type</span></span>|<span data-ttu-id="d56f4-119">描述</span><span class="sxs-lookup"><span data-stu-id="d56f4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d56f4-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="d56f4-120">TransactionId</span></span>|<span data-ttu-id="d56f4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d56f4-121">xs:string</span></span>|<span data-ttu-id="d56f4-122">CommittableTransaction 的 ID。</span><span class="sxs-lookup"><span data-stu-id="d56f4-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="d56f4-123">例外</span><span class="sxs-lookup"><span data-stu-id="d56f4-123">Exception</span></span>|<span data-ttu-id="d56f4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d56f4-124">xs:string</span></span>|<span data-ttu-id="d56f4-125">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="d56f4-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="d56f4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d56f4-126">AppDomain</span></span>|<span data-ttu-id="d56f4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d56f4-127">xs:string</span></span>|<span data-ttu-id="d56f4-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d56f4-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
