---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512224"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="5d42b-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="5d42b-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="5d42b-103">属性</span><span class="sxs-lookup"><span data-stu-id="5d42b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d42b-104">ID</span><span class="sxs-lookup"><span data-stu-id="5d42b-104">ID</span></span>|<span data-ttu-id="5d42b-105">3551</span><span class="sxs-lookup"><span data-stu-id="5d42b-105">3551</span></span>|  
|<span data-ttu-id="5d42b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5d42b-106">Keywords</span></span>|<span data-ttu-id="5d42b-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="5d42b-107">WFServices</span></span>|  
|<span data-ttu-id="5d42b-108">级别</span><span class="sxs-lookup"><span data-stu-id="5d42b-108">Level</span></span>|<span data-ttu-id="5d42b-109">信息</span><span class="sxs-lookup"><span data-stu-id="5d42b-109">Information</span></span>|  
|<span data-ttu-id="5d42b-110">通道</span><span class="sxs-lookup"><span data-stu-id="5d42b-110">Channel</span></span>|<span data-ttu-id="5d42b-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="5d42b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d42b-112">描述</span><span class="sxs-lookup"><span data-stu-id="5d42b-112">Description</span></span>  
 <span data-ttu-id="5d42b-113">指示书签恢复已失败。</span><span class="sxs-lookup"><span data-stu-id="5d42b-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="5d42b-114">服务实例准备好处理此特定操作时，将再次尝试该缓冲的接收操作。</span><span class="sxs-lookup"><span data-stu-id="5d42b-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d42b-115">消息</span><span class="sxs-lookup"><span data-stu-id="5d42b-115">Message</span></span>  
 <span data-ttu-id="5d42b-116">此时不能执行服务实例“%1”上的操作“%2”。</span><span class="sxs-lookup"><span data-stu-id="5d42b-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="5d42b-117">服务实例准备好处理此特定操作时，将进行另一个尝试。</span><span class="sxs-lookup"><span data-stu-id="5d42b-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d42b-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="5d42b-118">Details</span></span>  
  
|<span data-ttu-id="5d42b-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5d42b-119">Data Item Name</span></span>|<span data-ttu-id="5d42b-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5d42b-120">Data Item Type</span></span>|<span data-ttu-id="5d42b-121">描述</span><span class="sxs-lookup"><span data-stu-id="5d42b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d42b-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="5d42b-122">OperationName</span></span>|<span data-ttu-id="5d42b-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d42b-123">xs:string</span></span>|<span data-ttu-id="5d42b-124">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="5d42b-124">The name of the operation.</span></span>|  
|<span data-ttu-id="5d42b-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="5d42b-125">ServiceInstanceId</span></span>|<span data-ttu-id="5d42b-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d42b-126">xs:string</span></span>|<span data-ttu-id="5d42b-127">服务实例的 ID。</span><span class="sxs-lookup"><span data-stu-id="5d42b-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="5d42b-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d42b-128">AppDomain</span></span>|<span data-ttu-id="5d42b-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d42b-129">xs:string</span></span>|<span data-ttu-id="5d42b-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5d42b-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
