---
title: 常见容器设计原则
description: 了解很好的容器设计的基本原则，它是一个容器应承载只是一个过程。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 206963d63cf8e6ab4fc61b9176f1ba095868c6fc
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664297"
---
# <a name="common-container-design-principles"></a><span data-ttu-id="e1ff7-103">常见容器设计原则</span><span class="sxs-lookup"><span data-stu-id="e1ff7-103">Common container design principles</span></span>

<span data-ttu-id="e1ff7-104">提前到开发过程中获取的有几个值得一提的是有关如何使用容器的基本概念。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="e1ff7-105">容器等于一个过程</span><span class="sxs-lookup"><span data-stu-id="e1ff7-105">Container equals a process</span></span>

<span data-ttu-id="e1ff7-106">在容器模型中，容器表示单个进程。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="e1ff7-107">通过定义为进程边界的容器，在开始创建到横向，或批处理关闭时，进程使用的基元。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="e1ff7-108">当您运行的 Docker 容器时，您将看到[入口点](https://docs.docker.com/engine/reference/builder/#/entrypoint)定义。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="e1ff7-109">这会定义进程和容器的生存期。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="e1ff7-110">完成后，容器生命周期结束。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-110">When the process completes, the container life-cycle ends.</span></span> <span data-ttu-id="e1ff7-111">有长时间运行的进程，如 web 服务器和生存期较短的进程，例如批处理作业、 已作为 Microsoft Azure 实现[WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/)。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="e1ff7-112">如果进程失败，则容器结束，Orchestrator 接管。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="e1ff7-113">如果业务流程协调程序已指示要保留五个实例运行，并且其中一个出现故障，则 orchestrator 会创建另一个容器来替换失败的进程。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="e1ff7-114">在批处理作业中，使用参数启动该进程。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="e1ff7-115">进程完成，则工作完成。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="e1ff7-116">你可能会发现你希望在单个容器中运行的多个进程的方案。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="e1ff7-117">在任何体系结构文档中，永远不会"从来没有，"也不是始终将"always"。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="e1ff7-118">对于需要多个进程的情况下，一种常见模式是使用[监督程序](http://supervisord.org/)。</span><span class="sxs-lookup"><span data-stu-id="e1ff7-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e1ff7-119">[上一页](design-docker-applications.md)
>[下一页](monolithic-applications.md)</span><span class="sxs-lookup"><span data-stu-id="e1ff7-119">[Previous](design-docker-applications.md)
[Next](monolithic-applications.md)</span></span>