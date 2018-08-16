---
title: 为 Docker 容器选择 .NET Core 还是 .NET Framework
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 为 Docker 容器选择 .NET Core 还是 .NET Framework
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 0f6689468eda1dd1b12c24927e650b2b01381274
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104437"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a>为 Docker 容器选择 .NET Core 还是 .NET Framework

通过 .NET 生成服务器端容器化 Docker 应用程序时，有两种支持的实现方式：[.NET Framework](https://www.microsoft.com/net/download/framework) 和 [.NET Core](https://www.microsoft.com/net/download/core)。 这两者共享许多 .NET Standard 组件，可在它们之间共享代码。 但两者之间存在根本差异，可根据需要实现的目标选择实现方式。 本节提供有关何时选择每个实现方式的指南。


>[!div class="step-by-step"]
[上一页](../container-docker-introduction/docker-containers-images-registries.md)
[下一页](general-guidance.md)
