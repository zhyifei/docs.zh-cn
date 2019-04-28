---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008637"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="3e1f5-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="3e1f5-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="3e1f5-103">属性</span><span class="sxs-lookup"><span data-stu-id="3e1f5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e1f5-104">Id</span><span class="sxs-lookup"><span data-stu-id="3e1f5-104">ID</span></span>|<span data-ttu-id="3e1f5-105">1001</span><span class="sxs-lookup"><span data-stu-id="3e1f5-105">1001</span></span>|  
|<span data-ttu-id="3e1f5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3e1f5-106">Keywords</span></span>|<span data-ttu-id="3e1f5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3e1f5-107">WFRuntime</span></span>|  
|<span data-ttu-id="3e1f5-108">级别</span><span class="sxs-lookup"><span data-stu-id="3e1f5-108">Level</span></span>|<span data-ttu-id="3e1f5-109">信息</span><span class="sxs-lookup"><span data-stu-id="3e1f5-109">Information</span></span>|  
|<span data-ttu-id="3e1f5-110">通道</span><span class="sxs-lookup"><span data-stu-id="3e1f5-110">Channel</span></span>|<span data-ttu-id="3e1f5-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="3e1f5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e1f5-112">描述</span><span class="sxs-lookup"><span data-stu-id="3e1f5-112">Description</span></span>  
 <span data-ttu-id="3e1f5-113">指示工作流应用程序在“已关闭”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="3e1f5-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e1f5-114">消息</span><span class="sxs-lookup"><span data-stu-id="3e1f5-114">Message</span></span>  
 <span data-ttu-id="3e1f5-115">WorkflowInstance Id“%1”在“已关闭”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="3e1f5-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e1f5-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="3e1f5-116">Details</span></span>  
  
|<span data-ttu-id="3e1f5-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3e1f5-117">Data Item Name</span></span>|<span data-ttu-id="3e1f5-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3e1f5-118">Data Item Type</span></span>|<span data-ttu-id="3e1f5-119">描述</span><span class="sxs-lookup"><span data-stu-id="3e1f5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e1f5-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="3e1f5-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="3e1f5-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="3e1f5-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="3e1f5-122">应用程序域</span><span class="sxs-lookup"><span data-stu-id="3e1f5-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3e1f5-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3e1f5-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
