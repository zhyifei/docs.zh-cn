---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925224"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="eabcf-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="eabcf-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="eabcf-103">属性</span><span class="sxs-lookup"><span data-stu-id="eabcf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eabcf-104">Id</span><span class="sxs-lookup"><span data-stu-id="eabcf-104">ID</span></span>|<span data-ttu-id="eabcf-105">1008</span><span class="sxs-lookup"><span data-stu-id="eabcf-105">1008</span></span>|  
|<span data-ttu-id="eabcf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="eabcf-106">Keywords</span></span>|<span data-ttu-id="eabcf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="eabcf-107">WFRuntime</span></span>|  
|<span data-ttu-id="eabcf-108">级别</span><span class="sxs-lookup"><span data-stu-id="eabcf-108">Level</span></span>|<span data-ttu-id="eabcf-109">信息</span><span class="sxs-lookup"><span data-stu-id="eabcf-109">Information</span></span>|  
|<span data-ttu-id="eabcf-110">通道</span><span class="sxs-lookup"><span data-stu-id="eabcf-110">Channel</span></span>|<span data-ttu-id="eabcf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="eabcf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eabcf-112">描述</span><span class="sxs-lookup"><span data-stu-id="eabcf-112">Description</span></span>  
 <span data-ttu-id="eabcf-113">指示工作流应用程序已卸载。</span><span class="sxs-lookup"><span data-stu-id="eabcf-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eabcf-114">消息</span><span class="sxs-lookup"><span data-stu-id="eabcf-114">Message</span></span>  
 <span data-ttu-id="eabcf-115">WorkflowInstance Id“%1”已卸载。</span><span class="sxs-lookup"><span data-stu-id="eabcf-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eabcf-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="eabcf-116">Details</span></span>  
  
|<span data-ttu-id="eabcf-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="eabcf-117">Data Item Name</span></span>|<span data-ttu-id="eabcf-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="eabcf-118">Data Item Type</span></span>|<span data-ttu-id="eabcf-119">描述</span><span class="sxs-lookup"><span data-stu-id="eabcf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eabcf-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="eabcf-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="eabcf-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="eabcf-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="eabcf-122">应用程序域</span><span class="sxs-lookup"><span data-stu-id="eabcf-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="eabcf-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="eabcf-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
