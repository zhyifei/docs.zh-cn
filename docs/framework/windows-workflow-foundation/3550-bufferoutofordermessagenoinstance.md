---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755579"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="dd4e7-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="dd4e7-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="dd4e7-103">属性</span><span class="sxs-lookup"><span data-stu-id="dd4e7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd4e7-104">Id</span><span class="sxs-lookup"><span data-stu-id="dd4e7-104">ID</span></span>|<span data-ttu-id="dd4e7-105">3550</span><span class="sxs-lookup"><span data-stu-id="dd4e7-105">3550</span></span>|  
|<span data-ttu-id="dd4e7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="dd4e7-106">Keywords</span></span>|<span data-ttu-id="dd4e7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="dd4e7-107">WFServices</span></span>|  
|<span data-ttu-id="dd4e7-108">级别</span><span class="sxs-lookup"><span data-stu-id="dd4e7-108">Level</span></span>|<span data-ttu-id="dd4e7-109">信息</span><span class="sxs-lookup"><span data-stu-id="dd4e7-109">Information</span></span>|  
|<span data-ttu-id="dd4e7-110">通道</span><span class="sxs-lookup"><span data-stu-id="dd4e7-110">Channel</span></span>|<span data-ttu-id="dd4e7-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="dd4e7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dd4e7-112">描述</span><span class="sxs-lookup"><span data-stu-id="dd4e7-112">Description</span></span>  
 <span data-ttu-id="dd4e7-113">指示缓冲接收已失败。</span><span class="sxs-lookup"><span data-stu-id="dd4e7-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="dd4e7-114">服务实例准备好处理此特定操作时，将再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="dd4e7-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dd4e7-115">消息</span><span class="sxs-lookup"><span data-stu-id="dd4e7-115">Message</span></span>  
 <span data-ttu-id="dd4e7-116">此时不能执行操作“%1”。</span><span class="sxs-lookup"><span data-stu-id="dd4e7-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="dd4e7-117">服务实例准备好处理此特定操作时，将进行另一个尝试。</span><span class="sxs-lookup"><span data-stu-id="dd4e7-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dd4e7-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd4e7-118">Details</span></span>  
  
|<span data-ttu-id="dd4e7-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="dd4e7-119">Data Item Name</span></span>|<span data-ttu-id="dd4e7-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="dd4e7-120">Data Item Type</span></span>|<span data-ttu-id="dd4e7-121">描述</span><span class="sxs-lookup"><span data-stu-id="dd4e7-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dd4e7-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="dd4e7-122">OperationName</span></span>|<span data-ttu-id="dd4e7-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd4e7-123">xs:string</span></span>|<span data-ttu-id="dd4e7-124">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="dd4e7-124">The name of the operation.</span></span>|  
|<span data-ttu-id="dd4e7-125">应用程序域</span><span class="sxs-lookup"><span data-stu-id="dd4e7-125">AppDomain</span></span>|<span data-ttu-id="dd4e7-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd4e7-126">xs:string</span></span>|<span data-ttu-id="dd4e7-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="dd4e7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
