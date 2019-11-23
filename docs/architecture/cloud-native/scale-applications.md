---
title: 缩放云本机应用程序
description: 使用 Azure Kubernetes 服务和 Azure Functions 扩展云本机应用程序以经济高效的方式满足用户需求。
ms.date: 09/23/2019
ms.openlocfilehash: 5f4aac5804c5498c331787083c943a6ea1b69748
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841029"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="2596a-103">缩放云本机应用程序</span><span class="sxs-lookup"><span data-stu-id="2596a-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="2596a-104">迁移到云托管环境的最常 touted 的优点之一是可扩展性。</span><span class="sxs-lookup"><span data-stu-id="2596a-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="2596a-105">最常通过将应用程序分解成多个小部分来实现可伸缩性，或允许应用程序在每个用户的会过度降级性能的情况下实现额外的用户负载。</span><span class="sxs-lookup"><span data-stu-id="2596a-105">Scalability, or the ability for an application to accept additional user load without unduly degrading performance for each user, is most often achieved by breaking up applications into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="2596a-106">在本章中，我们将介绍一些技术，这些技术可让云本机应用程序进行缩放以满足用户需求。</span><span class="sxs-lookup"><span data-stu-id="2596a-106">In this chapter, we introduce the technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="2596a-107">这些技术包括：</span><span class="sxs-lookup"><span data-stu-id="2596a-107">These technologies include:</span></span>

- <span data-ttu-id="2596a-108">容器</span><span class="sxs-lookup"><span data-stu-id="2596a-108">Containers</span></span>
- <span data-ttu-id="2596a-109">协调器</span><span class="sxs-lookup"><span data-stu-id="2596a-109">Orchestrators</span></span>
- <span data-ttu-id="2596a-110">无服务器计算</span><span class="sxs-lookup"><span data-stu-id="2596a-110">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2596a-111">[上一页](centralized-configuration.md)
>[下一页](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="2596a-111">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
