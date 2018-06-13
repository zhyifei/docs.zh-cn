---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511586"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="5101f-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="5101f-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="5101f-103">属性</span><span class="sxs-lookup"><span data-stu-id="5101f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5101f-104">ID</span><span class="sxs-lookup"><span data-stu-id="5101f-104">ID</span></span>|<span data-ttu-id="5101f-105">4208</span><span class="sxs-lookup"><span data-stu-id="5101f-105">4208</span></span>|  
|<span data-ttu-id="5101f-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5101f-106">Keywords</span></span>|<span data-ttu-id="5101f-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5101f-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5101f-108">级别</span><span class="sxs-lookup"><span data-stu-id="5101f-108">Level</span></span>|<span data-ttu-id="5101f-109">信息</span><span class="sxs-lookup"><span data-stu-id="5101f-109">Information</span></span>|  
|<span data-ttu-id="5101f-110">通道</span><span class="sxs-lookup"><span data-stu-id="5101f-110">Channel</span></span>|<span data-ttu-id="5101f-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="5101f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5101f-112">描述</span><span class="sxs-lookup"><span data-stu-id="5101f-112">Description</span></span>  
 <span data-ttu-id="5101f-113">指示 SQL 提供程序由于 SQL 错误正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="5101f-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5101f-114">消息</span><span class="sxs-lookup"><span data-stu-id="5101f-114">Message</span></span>  
 <span data-ttu-id="5101f-115">因 SQL 错误号 %1，正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="5101f-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5101f-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="5101f-116">Details</span></span>  
  
|<span data-ttu-id="5101f-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5101f-117">Data Item Name</span></span>|<span data-ttu-id="5101f-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5101f-118">Data Item Type</span></span>|<span data-ttu-id="5101f-119">描述</span><span class="sxs-lookup"><span data-stu-id="5101f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5101f-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="5101f-120">ErrorNumber</span></span>|<span data-ttu-id="5101f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5101f-121">xs:string</span></span>|<span data-ttu-id="5101f-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="5101f-122">The SQL error number.</span></span>|  
|<span data-ttu-id="5101f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5101f-123">AppDomain</span></span>|<span data-ttu-id="5101f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5101f-124">xs:string</span></span>|<span data-ttu-id="5101f-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5101f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
