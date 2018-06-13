---
title: 1037 - RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: 7a94c917157904c5cb84105c41842657a534c973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509595"
---
# <a name="1037---runtimetransactioncomplete"></a><span data-ttu-id="2b56d-102">1037 - RuntimeTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="2b56d-102">1037 - RuntimeTransactionComplete</span></span>
## <a name="properties"></a><span data-ttu-id="2b56d-103">属性</span><span class="sxs-lookup"><span data-stu-id="2b56d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b56d-104">ID</span><span class="sxs-lookup"><span data-stu-id="2b56d-104">ID</span></span>|<span data-ttu-id="2b56d-105">1037</span><span class="sxs-lookup"><span data-stu-id="2b56d-105">1037</span></span>|  
|<span data-ttu-id="2b56d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2b56d-106">Keywords</span></span>|<span data-ttu-id="2b56d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2b56d-107">WFRuntime</span></span>|  
|<span data-ttu-id="2b56d-108">级别</span><span class="sxs-lookup"><span data-stu-id="2b56d-108">Level</span></span>|<span data-ttu-id="2b56d-109">详细</span><span class="sxs-lookup"><span data-stu-id="2b56d-109">Verbose</span></span>|  
|<span data-ttu-id="2b56d-110">通道</span><span class="sxs-lookup"><span data-stu-id="2b56d-110">Channel</span></span>|<span data-ttu-id="2b56d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="2b56d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b56d-112">描述</span><span class="sxs-lookup"><span data-stu-id="2b56d-112">Description</span></span>  
 <span data-ttu-id="2b56d-113">指示运行时事务已完成。</span><span class="sxs-lookup"><span data-stu-id="2b56d-113">Indicates the runtime transaction has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b56d-114">消息</span><span class="sxs-lookup"><span data-stu-id="2b56d-114">Message</span></span>  
 <span data-ttu-id="2b56d-115">运行时事务已完成，状态为“%1”。</span><span class="sxs-lookup"><span data-stu-id="2b56d-115">The runtime transaction has completed with the state '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b56d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="2b56d-116">Details</span></span>  
  
|<span data-ttu-id="2b56d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2b56d-117">Data Item Name</span></span>|<span data-ttu-id="2b56d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2b56d-118">Data Item Type</span></span>|<span data-ttu-id="2b56d-119">描述</span><span class="sxs-lookup"><span data-stu-id="2b56d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2b56d-120">状态</span><span class="sxs-lookup"><span data-stu-id="2b56d-120">State</span></span>|<span data-ttu-id="2b56d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b56d-121">xs:string</span></span>|<span data-ttu-id="2b56d-122">事务的状态。</span><span class="sxs-lookup"><span data-stu-id="2b56d-122">The state of the transaction.</span></span>|  
|<span data-ttu-id="2b56d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2b56d-123">AppDomain</span></span>|<span data-ttu-id="2b56d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b56d-124">xs:string</span></span>|<span data-ttu-id="2b56d-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2b56d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
