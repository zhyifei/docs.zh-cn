---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510074"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="53c13-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="53c13-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="53c13-103">属性</span><span class="sxs-lookup"><span data-stu-id="53c13-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53c13-104">ID</span><span class="sxs-lookup"><span data-stu-id="53c13-104">ID</span></span>|<span data-ttu-id="53c13-105">1002</span><span class="sxs-lookup"><span data-stu-id="53c13-105">1002</span></span>|  
|<span data-ttu-id="53c13-106">关键字</span><span class="sxs-lookup"><span data-stu-id="53c13-106">Keywords</span></span>|<span data-ttu-id="53c13-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="53c13-107">WFRuntime</span></span>|  
|<span data-ttu-id="53c13-108">级别</span><span class="sxs-lookup"><span data-stu-id="53c13-108">Level</span></span>|<span data-ttu-id="53c13-109">信息</span><span class="sxs-lookup"><span data-stu-id="53c13-109">Information</span></span>|  
|<span data-ttu-id="53c13-110">通道</span><span class="sxs-lookup"><span data-stu-id="53c13-110">Channel</span></span>|<span data-ttu-id="53c13-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="53c13-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="53c13-112">描述</span><span class="sxs-lookup"><span data-stu-id="53c13-112">Description</span></span>  
 <span data-ttu-id="53c13-113">指示工作流应用程序因出现异常而在“出错”状态下终止。</span><span class="sxs-lookup"><span data-stu-id="53c13-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="53c13-114">消息</span><span class="sxs-lookup"><span data-stu-id="53c13-114">Message</span></span>  
 <span data-ttu-id="53c13-115">WorkflowApplication Id“%1”已终止。</span><span class="sxs-lookup"><span data-stu-id="53c13-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="53c13-116">该应用程序因出现异常而在“出错”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="53c13-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="53c13-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="53c13-117">Details</span></span>  
  
|<span data-ttu-id="53c13-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="53c13-118">Data Item Name</span></span>|<span data-ttu-id="53c13-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="53c13-119">Data Item Type</span></span>|<span data-ttu-id="53c13-120">描述</span><span class="sxs-lookup"><span data-stu-id="53c13-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="53c13-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="53c13-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="53c13-122">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="53c13-122">The workflow application id</span></span>|  
|<span data-ttu-id="53c13-123">例外</span><span class="sxs-lookup"><span data-stu-id="53c13-123">Exception</span></span>|`xs:string`|<span data-ttu-id="53c13-124">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="53c13-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="53c13-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="53c13-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="53c13-126">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="53c13-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
