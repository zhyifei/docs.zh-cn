---
title: 缩放云本机应用程序
description: 使用 Azure Kubernetes 服务和 Azure Functions 扩展云本机应用程序以经济高效的方式满足用户需求。
ms.date: 04/13/2020
ms.openlocfilehash: 91d925778e9dfcf8a1ec2486fe8961037409f207
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199932"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="b5dc9-103">缩放云本机应用程序</span><span class="sxs-lookup"><span data-stu-id="b5dc9-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b5dc9-104">迁移到云托管环境的最常 touted 的优点之一是可扩展性。</span><span class="sxs-lookup"><span data-stu-id="b5dc9-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="b5dc9-105">可伸缩性，或允许应用程序在不影响每个用户的性能的情况下接受额外用户负载的能力。</span><span class="sxs-lookup"><span data-stu-id="b5dc9-105">Scalability, or the ability for an application to accept additional user load without compromising performance for each user.</span></span> <span data-ttu-id="b5dc9-106">最常见的实现方法是将应用程序分解成小部分，每个小部分都可以获得所需的任何资源。</span><span class="sxs-lookup"><span data-stu-id="b5dc9-106">It's most often achieved by breaking up an application into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="b5dc9-107">云供应商可以随时随地和世界各地实现巨大的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="b5dc9-107">Cloud vendors enable massive scalability anytime and anywhere in the world.</span></span>

 <span data-ttu-id="b5dc9-108">在本章中，我们将讨论使云原生应用程序可进行缩放以满足用户需求的技术。</span><span class="sxs-lookup"><span data-stu-id="b5dc9-108">In this chapter, we discuss technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="b5dc9-109">这些技术包括：</span><span class="sxs-lookup"><span data-stu-id="b5dc9-109">These technologies include:</span></span>

- <span data-ttu-id="b5dc9-110">容器</span><span class="sxs-lookup"><span data-stu-id="b5dc9-110">Containers</span></span>
- <span data-ttu-id="b5dc9-111">协调器</span><span class="sxs-lookup"><span data-stu-id="b5dc9-111">Orchestrators</span></span>
- <span data-ttu-id="b5dc9-112">无服务器计算</span><span class="sxs-lookup"><span data-stu-id="b5dc9-112">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b5dc9-113">[上一页](centralized-configuration.md)
>[下一页](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="b5dc9-113">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
