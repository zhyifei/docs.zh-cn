---
title: "面向服务的体系结构"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |面向服务的体系结构"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a>面向服务的体系结构 

面向服务的体系结构 (SOA) 的使用过度的术语，目的是不同的人的不同内容。 但视为公分，SOA 意味着通过将其分解到多 （通常作为 HTTP 服务） 可被归类为如子系统或层的不同类型的多个服务构建你的应用程序。

这些服务现在可部署为 Docker 容器，这可解决部署问题，因为容器映像中包含的所有依赖项。 但是，当你需要纵向扩展 SOA 应用程序，你可能具有可伸缩性和可用性挑战，如果你要部署基于单个 Docker 主机上。 这是 Docker 群集软件或编排器将帮助你 out，我们介绍微服务的部署方法的位置的后面部分中所述。

Docker 容器是有用的 （但不是必需的） 传统的面向服务的体系结构和更高级的微服务体系结构。

微服务派生 SOA，但 SOA 不同于微服务体系结构。 功能，如大中央代理、 级别的组织的中央 orchestrators 和[企业服务总线 (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus)很平常的 SOA。 但在大多数情况下，这些事务是 microservice 社区中的反模式。 事实上，有些人认为"微服务体系结构得当的 SOA。"

本指南重点微服务，因为 SOA 方法是不太说明性比的要求和在微服务体系结构中使用的技术。 如果你知道如何生成基于微服务构成的应用程序，你还了解如何构建一个简单的面向服务的应用程序。




>[!div class="step-by-step"]
[以前](docker-应用程序的状态-data.md) [下一步] (微服务 architecture.md)
