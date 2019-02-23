---
title: SOA 应用程序
description: 请记住容器也可以是 SOA 应用程序的有用的部署选项。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 353ba738143b7dcd92c7c75ac27ea6a7370f9da6
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745828"
---
# <a name="service-oriented-applications"></a>面向服务的应用程序

面向服务的体系结构 (SOA) 是一个使用过度的术语，意味着不同的人很多不同的理解。 但相同的理解，SOA 意味着通过分解为可进行分类等子系统的不同类型中，或在其他情况下，作为层的多个服务 （通常为 HTTP 服务） 构建的应用程序体系结构。

现在，可以将这些服务部署为 Docker 容器，解决与部署相关的问题，因为容器映像中包含了所有依赖项。 但是，当您需要向外扩展 Soa，如果要部署基于单个实例可能遇到难题。 可以使用 Docker 群集软件或业务流程协调程序处理这一挑战。 我们将探讨微服务方法时，我们来看看下一节中更详细地业务流程协调程序。

对于传统的面向服务的体系结构和更高级的微服务体系结构，Docker 容器都是有用的（但不是必需的）。

在一天结束时，容器聚类分析解决方案是适用于这两种传统 SOA 的体系结构以及在其中每个微服务拥有它的数据模型的更高级的微服务体系结构。 和得益于多个数据库，您还可以向外扩展而不是使用共享的 SOA 服务的整体式数据库的数据层。 但是，有关将数据拆分的讨论是纯粹有关体系结构和设计。

>[!div class="step-by-step"]
>[上一页](state-and-data-in-docker-applications.md)
>[下一页](orchestrate-high-scalability-availability.md)
