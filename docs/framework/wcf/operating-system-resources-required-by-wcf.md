---
title: WCF 所要求的操作系统资源
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961139"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="07f0f-102">WCF 所要求的操作系统资源</span><span class="sxs-lookup"><span data-stu-id="07f0f-102">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="07f0f-103">Windows Communication Foundation （WCF）依赖于操作系统提供的多个资源才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="07f0f-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="07f0f-104">下表列出了这些资源：</span><span class="sxs-lookup"><span data-stu-id="07f0f-104">The following table lists those resources:</span></span>

|<span data-ttu-id="07f0f-105">资源</span><span class="sxs-lookup"><span data-stu-id="07f0f-105">Resource</span></span>|<span data-ttu-id="07f0f-106">描述</span><span class="sxs-lookup"><span data-stu-id="07f0f-106">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="07f0f-107">Microsoft 分布式事务协调器 (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="07f0f-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="07f0f-108">支持 OleTx 事务所必需。</span><span class="sxs-lookup"><span data-stu-id="07f0f-108">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="07f0f-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="07f0f-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="07f0f-110">如果希望使用 IIS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="07f0f-110">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="07f0f-111">Windows 进程激活服务 (WAS)</span><span class="sxs-lookup"><span data-stu-id="07f0f-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="07f0f-112">如果希望使用 WAS 来承载应用程序，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="07f0f-112">Required if you want to use WAS to host your application.</span></span>|
