---
title: 常见容器设计原则
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a289cdafc88abe8629638a84eff184829362e16
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="common-container-design-principles"></a>常见容器设计原则

继续的陷入开发过程中有几个值得一提的是关于如何使用容器的基本概念。

## <a name="container-equals-a-process"></a>容器等于进程

在容器模型中，容器表示单个进程。 通过定义为进程边界的容器，在开始创建到缩放，或批处理关闭时，进程使用的基元。 运行 Docker 容器时，你将看到[入口点](https://docs.docker.com/engine/reference/builder/#/entrypoint)定义。 这将定义在过程和容器的生存期。 当进程完成后时，容器生命周期结束。 有长时间运行的进程，如 web 服务器和生存期较短的进程，例如批处理作业、 已为 Microsoft Azure 实现[WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/)。 如果进程失败，则容器结束，Orchestrator 接管。 如果 orchestrator 已指示要保留五个实例运行，并且其中一个发生故障，orchestrator 将创建另一个容器来替换失败的进程。 在批处理作业中，使用参数启动该进程。 进程完成，则工作完成。

你可能会发现你希望在单个容器中运行的多个进程的方案。 在任何体系结构文档中，存在不从不"，"也不是始终将"始终"。 对于需要多个进程的情况下，一种常见模式是使用[Supervisor](http://supervisord.org/)。


>[!div class="step-by-step"]
[以前](设计-docker-applications.md) [下一步] (整体 applications.md)
