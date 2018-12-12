---
title: SOA 应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 7f88daaf0787cf780e7ab9602f35ae4e6ab8308c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155309"
---
# <a name="soa-applications"></a>SOA 应用程序

SOA 是一个使用过度的术语，意味着不同的人这么多不同的理解。 但至少和通用标准，SOA，或服务导向，平均值作为该您结构通过将它分解 （通常为 HTTP 服务） 可以分为不同类型的多个服务中的应用程序的体系结构，如子系统或者，在其他情况下，作为层。

现在，你可以为 Docker 容器，这可解决与部署相关的问题，因为所有依赖项都将包含在容器映像部署这些服务。 但是，当您需要进行横向扩展 Soa，如果要部署基于单个实例可能会遇到难题。 这是 Docker 群集软件或业务流程协调程序将帮助你。 我们将介绍这在下一节中更详细地探讨如何使用微服务方法时。

在一天结束时，容器聚类分析解决方案可用于这两种传统 SOA 体系结构或在其中每个微服务拥有它的数据模型的更高级的微服务体系结构。 并且，由于多个数据库，您还可以向外缩放而不是使用共享的 SOA 服务的整体式数据库的数据层。 但是，有关将数据拆分的讨论是纯粹有关体系结构和设计。

>[!div class="step-by-step"]
>[上一页](state-and-data-in-docker-applications.md)
>[下一页](orchestrate-high-scalability-availability.md)