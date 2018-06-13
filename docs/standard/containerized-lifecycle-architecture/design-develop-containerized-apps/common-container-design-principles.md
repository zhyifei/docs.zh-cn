---
title: 常见容器设计原则
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: c67986b1deb504f2b05f2903a263bf1a91f70b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568116"
---
# <a name="common-container-design-principles"></a><span data-ttu-id="d8af3-103">常见容器设计原则</span><span class="sxs-lookup"><span data-stu-id="d8af3-103">Common container design principles</span></span>

<span data-ttu-id="d8af3-104">继续的陷入开发过程中有几个值得一提的是关于如何使用容器的基本概念。</span><span class="sxs-lookup"><span data-stu-id="d8af3-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="d8af3-105">容器等于进程</span><span class="sxs-lookup"><span data-stu-id="d8af3-105">Container equals a process</span></span>

<span data-ttu-id="d8af3-106">在容器模型中，容器表示单个进程。</span><span class="sxs-lookup"><span data-stu-id="d8af3-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="d8af3-107">通过定义为进程边界的容器，在开始创建到缩放，或批处理关闭时，进程使用的基元。</span><span class="sxs-lookup"><span data-stu-id="d8af3-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="d8af3-108">运行 Docker 容器时，你将看到[入口点](https://docs.docker.com/engine/reference/builder/#/entrypoint)定义。</span><span class="sxs-lookup"><span data-stu-id="d8af3-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="d8af3-109">这将定义在过程和容器的生存期。</span><span class="sxs-lookup"><span data-stu-id="d8af3-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="d8af3-110">当进程完成后时，容器生命周期结束。</span><span class="sxs-lookup"><span data-stu-id="d8af3-110">When the process completes, the container life cycle ends.</span></span> <span data-ttu-id="d8af3-111">有长时间运行的进程，如 web 服务器和生存期较短的进程，例如批处理作业、 已为 Microsoft Azure 实现[WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/)。</span><span class="sxs-lookup"><span data-stu-id="d8af3-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="d8af3-112">如果进程失败，则容器结束，Orchestrator 接管。</span><span class="sxs-lookup"><span data-stu-id="d8af3-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="d8af3-113">如果 orchestrator 已指示要保留五个实例运行，并且其中一个发生故障，orchestrator 将创建另一个容器来替换失败的进程。</span><span class="sxs-lookup"><span data-stu-id="d8af3-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="d8af3-114">在批处理作业中，使用参数启动该进程。</span><span class="sxs-lookup"><span data-stu-id="d8af3-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="d8af3-115">进程完成，则工作完成。</span><span class="sxs-lookup"><span data-stu-id="d8af3-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="d8af3-116">你可能会发现你希望在单个容器中运行的多个进程的方案。</span><span class="sxs-lookup"><span data-stu-id="d8af3-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="d8af3-117">在任何体系结构文档中，存在不从不"，"也不是始终将"始终"。</span><span class="sxs-lookup"><span data-stu-id="d8af3-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="d8af3-118">对于需要多个进程的情况下，一种常见模式是使用[Supervisor](http://supervisord.org/)。</span><span class="sxs-lookup"><span data-stu-id="d8af3-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d8af3-119">[以前] (design-docker-applications.md) [下一步] (monolithic-applications.md)</span><span class="sxs-lookup"><span data-stu-id="d8af3-119">[Previous] (design-docker-applications.md) [Next] (monolithic-applications.md)</span></span>
