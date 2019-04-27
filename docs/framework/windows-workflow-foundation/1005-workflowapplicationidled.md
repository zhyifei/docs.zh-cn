---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008598"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="8e2d5-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="8e2d5-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="8e2d5-103">属性</span><span class="sxs-lookup"><span data-stu-id="8e2d5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e2d5-104">Id</span><span class="sxs-lookup"><span data-stu-id="8e2d5-104">ID</span></span>|<span data-ttu-id="8e2d5-105">1005</span><span class="sxs-lookup"><span data-stu-id="8e2d5-105">1005</span></span>|  
|<span data-ttu-id="8e2d5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8e2d5-106">Keywords</span></span>|<span data-ttu-id="8e2d5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8e2d5-107">WFRuntime</span></span>|  
|<span data-ttu-id="8e2d5-108">级别</span><span class="sxs-lookup"><span data-stu-id="8e2d5-108">Level</span></span>|<span data-ttu-id="8e2d5-109">信息</span><span class="sxs-lookup"><span data-stu-id="8e2d5-109">Information</span></span>|  
|<span data-ttu-id="8e2d5-110">通道</span><span class="sxs-lookup"><span data-stu-id="8e2d5-110">Channel</span></span>|<span data-ttu-id="8e2d5-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="8e2d5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8e2d5-112">描述</span><span class="sxs-lookup"><span data-stu-id="8e2d5-112">Description</span></span>  
 <span data-ttu-id="8e2d5-113">指示工作流应用程序已处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="8e2d5-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8e2d5-114">消息</span><span class="sxs-lookup"><span data-stu-id="8e2d5-114">Message</span></span>  
 <span data-ttu-id="8e2d5-115">WorkflowApplication ID“%1”变为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="8e2d5-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8e2d5-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="8e2d5-116">Details</span></span>  
  
|<span data-ttu-id="8e2d5-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8e2d5-117">Data Item Name</span></span>|<span data-ttu-id="8e2d5-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8e2d5-118">Data Item Type</span></span>|<span data-ttu-id="8e2d5-119">描述</span><span class="sxs-lookup"><span data-stu-id="8e2d5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8e2d5-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="8e2d5-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="8e2d5-121">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="8e2d5-121">The workflow application id</span></span>|  
|<span data-ttu-id="8e2d5-122">应用程序域</span><span class="sxs-lookup"><span data-stu-id="8e2d5-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8e2d5-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8e2d5-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
