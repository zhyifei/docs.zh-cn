---
title: SOA 应用程序
description: 请记住，容器也可以是 SOA 应用程序的有用部署选项。
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644765"
---
# <a name="service-oriented-applications"></a>面向服务的应用程序

面向服务的体系结构 (SOA) 是一个使用过度的术语，不同的人对它的理解不尽相同。 但相同的理解是，SOA 意味着通过将应用程序的体系结构分解为多个服务（通常为 HTTP 服务），将其分为不同类型（例如子系统，或者在其他情况下分类为层），从而来划分应用程序的结构。

现在，你可以将这些服务部署为 Docker 容器，从而解决与部署相关的问题，因为所有依赖项都包含在容器映像中。 但是，当你需要扩展 SOA 时，如果基于单个实例进行部署，则可能会遇到难题。 可以使用 Docker 群集软件或业务流程协调程序来处理此难题。 当我们探索微服务方法时，我们将在下一部分中更详细地讨论业务流程协调程序。

对于传统的面向服务的体系结构和更高级的微服务体系结构，Docker 容器都是有用的（但不是必需的）。

归根结底，容器群集解决方案对于传统的 SOA 体系结构和更高级的微服务体系结构都很有用，其中每个微服务都拥有其数据模型。 由于有多个数据库，还可以扩展数据层，而不必使用 SOA 服务共享的单一数据库。 但是，关于拆分数据的讨论纯粹是关于架构和设计。

>[!div class="step-by-step"]
>[上一页](state-and-data-in-docker-applications.md)
>[下一页](orchestrate-high-scalability-availability.md)
