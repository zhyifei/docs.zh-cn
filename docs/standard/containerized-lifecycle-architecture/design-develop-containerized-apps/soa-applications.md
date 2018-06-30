---
title: SOA 应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 276071a5d55015f2feecc27020ad614684907b4c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105206"
---
# <a name="soa-applications"></a>SOA 应用程序

SOA 是的使用过度的术语，意味着要对不同的人是许多不同的事物。 但该你结构的您的应用程序将它分解可以分为不同类型的多个服务 （通常作为 HTTP 服务） 中的体系结构最少和作为公分、 SOA，或面向服务、 平均值如子系统或者，在其他情况下，为层。

现在，你可以为 Docker 容器，这可解决与部署相关的问题，因为所有依赖项是包含在容器映像部署这些服务。 但是，当你需要进行横向扩展 SOAs，则可能遇到挑战，如果你要部署基于单个实例。 这是群集软件或 orchestrator 的 Docker 将帮助你。 当我们检查微服务方法，我们将在此查看更详细地下一节介绍。

在一天结束时，容器聚类分析解决方案可为这两种传统 SOA 的体系结构或在其中每个微服务拥有其数据模型的更高级的微服务体系结构。 和，得益于多个数据库，你还可以向外扩展而不是使用由 SOA 服务共享的单一数据库的数据层。 但是，有关将数据拆分讨论是纯粹有关体系结构和设计。


>[!div class="step-by-step"]
[上一页](state-and-data-in-docker-applications.md)
[下一页](orchestrate-high-scalability-availability.md)
