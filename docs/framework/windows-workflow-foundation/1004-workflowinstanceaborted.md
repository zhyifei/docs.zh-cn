---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008611"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="c20e3-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="c20e3-102">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="c20e3-103">属性</span><span class="sxs-lookup"><span data-stu-id="c20e3-103">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="c20e3-104">Id</span><span class="sxs-lookup"><span data-stu-id="c20e3-104">ID</span></span>|<span data-ttu-id="c20e3-105">1004</span><span class="sxs-lookup"><span data-stu-id="c20e3-105">1004</span></span>|
|<span data-ttu-id="c20e3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c20e3-106">Keywords</span></span>|<span data-ttu-id="c20e3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c20e3-107">WFRuntime</span></span>|
|<span data-ttu-id="c20e3-108">级别</span><span class="sxs-lookup"><span data-stu-id="c20e3-108">Level</span></span>|<span data-ttu-id="c20e3-109">信息</span><span class="sxs-lookup"><span data-stu-id="c20e3-109">Information</span></span>|
|<span data-ttu-id="c20e3-110">通道</span><span class="sxs-lookup"><span data-stu-id="c20e3-110">Channel</span></span>|<span data-ttu-id="c20e3-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c20e3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="c20e3-112">描述</span><span class="sxs-lookup"><span data-stu-id="c20e3-112">Description</span></span>

<span data-ttu-id="c20e3-113">指示工作流实例已中止并且具有异常。</span><span class="sxs-lookup"><span data-stu-id="c20e3-113">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="c20e3-114">消息</span><span class="sxs-lookup"><span data-stu-id="c20e3-114">Message</span></span>

<span data-ttu-id="c20e3-115">WorkflowInstance Id“%1”因出现异常而中止。</span><span class="sxs-lookup"><span data-stu-id="c20e3-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="c20e3-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c20e3-116">Details</span></span>

|<span data-ttu-id="c20e3-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c20e3-117">Data Item Name</span></span>|<span data-ttu-id="c20e3-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c20e3-118">Data Item Type</span></span>|<span data-ttu-id="c20e3-119">描述</span><span class="sxs-lookup"><span data-stu-id="c20e3-119">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="c20e3-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="c20e3-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="c20e3-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="c20e3-121">The instance id for the workflow</span></span>|
|<span data-ttu-id="c20e3-122">例外</span><span class="sxs-lookup"><span data-stu-id="c20e3-122">Exception</span></span>|`xs:string`|<span data-ttu-id="c20e3-123">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="c20e3-123">The exception details for the exception</span></span>|
|<span data-ttu-id="c20e3-124">应用程序域</span><span class="sxs-lookup"><span data-stu-id="c20e3-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c20e3-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c20e3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
