---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509289"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="42a17-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="42a17-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="42a17-103">属性</span><span class="sxs-lookup"><span data-stu-id="42a17-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42a17-104">ID</span><span class="sxs-lookup"><span data-stu-id="42a17-104">ID</span></span>|<span data-ttu-id="42a17-105">1005</span><span class="sxs-lookup"><span data-stu-id="42a17-105">1005</span></span>|  
|<span data-ttu-id="42a17-106">关键字</span><span class="sxs-lookup"><span data-stu-id="42a17-106">Keywords</span></span>|<span data-ttu-id="42a17-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="42a17-107">WFRuntime</span></span>|  
|<span data-ttu-id="42a17-108">级别</span><span class="sxs-lookup"><span data-stu-id="42a17-108">Level</span></span>|<span data-ttu-id="42a17-109">信息</span><span class="sxs-lookup"><span data-stu-id="42a17-109">Information</span></span>|  
|<span data-ttu-id="42a17-110">通道</span><span class="sxs-lookup"><span data-stu-id="42a17-110">Channel</span></span>|<span data-ttu-id="42a17-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="42a17-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42a17-112">描述</span><span class="sxs-lookup"><span data-stu-id="42a17-112">Description</span></span>  
 <span data-ttu-id="42a17-113">指示工作流应用程序已处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="42a17-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42a17-114">消息</span><span class="sxs-lookup"><span data-stu-id="42a17-114">Message</span></span>  
 <span data-ttu-id="42a17-115">WorkflowApplication ID“%1”变为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="42a17-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42a17-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="42a17-116">Details</span></span>  
  
|<span data-ttu-id="42a17-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="42a17-117">Data Item Name</span></span>|<span data-ttu-id="42a17-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="42a17-118">Data Item Type</span></span>|<span data-ttu-id="42a17-119">描述</span><span class="sxs-lookup"><span data-stu-id="42a17-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42a17-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="42a17-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="42a17-121">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="42a17-121">The workflow application id</span></span>|  
|<span data-ttu-id="42a17-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="42a17-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="42a17-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="42a17-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
