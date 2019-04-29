---
title: 4207 - MaximumRetriesExceededForSqlCommand
ms.date: 03/30/2017
ms.assetid: 8c8bee26-9ad4-4e01-bd16-0e1fd510fb6b
ms.openlocfilehash: b763e087d8ead2bcc0fadd1d0223ae1bd58c9fd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774304"
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a><span data-ttu-id="56f90-102">4207 - MaximumRetriesExceededForSqlCommand</span><span class="sxs-lookup"><span data-stu-id="56f90-102">4207 - MaximumRetriesExceededForSqlCommand</span></span>
## <a name="properties"></a><span data-ttu-id="56f90-103">属性</span><span class="sxs-lookup"><span data-stu-id="56f90-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56f90-104">Id</span><span class="sxs-lookup"><span data-stu-id="56f90-104">ID</span></span>|<span data-ttu-id="56f90-105">4207</span><span class="sxs-lookup"><span data-stu-id="56f90-105">4207</span></span>|  
|<span data-ttu-id="56f90-106">关键字</span><span class="sxs-lookup"><span data-stu-id="56f90-106">Keywords</span></span>|<span data-ttu-id="56f90-107">配额，FInstanceStore</span><span class="sxs-lookup"><span data-stu-id="56f90-107">Quota, WFInstanceStore</span></span>|  
|<span data-ttu-id="56f90-108">级别</span><span class="sxs-lookup"><span data-stu-id="56f90-108">Level</span></span>|<span data-ttu-id="56f90-109">信息</span><span class="sxs-lookup"><span data-stu-id="56f90-109">Information</span></span>|  
|<span data-ttu-id="56f90-110">通道</span><span class="sxs-lookup"><span data-stu-id="56f90-110">Channel</span></span>|<span data-ttu-id="56f90-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="56f90-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56f90-112">描述</span><span class="sxs-lookup"><span data-stu-id="56f90-112">Description</span></span>  
 <span data-ttu-id="56f90-113">指示 SQL 提供程序正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="56f90-113">Indicates SQL provider is giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56f90-114">消息</span><span class="sxs-lookup"><span data-stu-id="56f90-114">Message</span></span>  
 <span data-ttu-id="56f90-115">正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="56f90-115">Giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56f90-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="56f90-116">Details</span></span>  
  
|<span data-ttu-id="56f90-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="56f90-117">Data Item Name</span></span>|<span data-ttu-id="56f90-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="56f90-118">Data Item Type</span></span>|<span data-ttu-id="56f90-119">描述</span><span class="sxs-lookup"><span data-stu-id="56f90-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56f90-120">应用程序域</span><span class="sxs-lookup"><span data-stu-id="56f90-120">AppDomain</span></span>|<span data-ttu-id="56f90-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="56f90-121">xs:string</span></span>|<span data-ttu-id="56f90-122">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="56f90-122">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
