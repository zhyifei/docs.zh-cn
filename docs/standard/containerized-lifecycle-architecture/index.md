---
title: 容器和 Docker 简介
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: c2a6b9802bbb995939d33c5c40ef9c1afa1620e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148816"
---
# <a name="introduction-to-containers-and-docker"></a>容器和 Docker 简介

容器化是软件开发的一种方法，通过该方法可将应用程序或服务、其依赖项及其配置（抽象化为部署清单文件）一起打包为容器映像。 然后可将容器化应用程序作为单元进行测试，并将其作为容器映像实例部署到主机操作系统。

就像运输业借助船只、火车或卡车运输使用标准化容器运输货物而不论其内部的货物一样，软件容器充当软件的标准单位，其中可以包含不同的代码和依赖项。 将软件放入容器，让开发人员和 IT 专业人士只需进行极少修改或无需修改，即可将这些容器部署到不同环境。

容器还会在共享操作系统 (OS) 上将应用程序彼此隔离开。 容器化应用程序在容器主机上运行，而容器主机在 OS（Linux 或 Windows）上运行。 因此，容器的占用比虚拟机 (VM) 映像小得多。

每个容器可以运行整个 Web 应用或服务，如图 1-1 所示。

![](./media/image1.png)

图 1-1:在一个容器主机上运行多个容器

在此示例中，Docker 主机是容器主机，而 App 1、App 2、Svc 1 和 Svc 2 是容器化应用程序或服务。

可从容器化获得的另一个优势是可伸缩性。 通过为短期任务创建新容器，可以快速横向扩展。 从应用程序的角度来看，实例化映像（创建容器）类似于实例化服务或 Web 应用等进程。 出于可靠性考虑，但是，跨多个主机服务器，运行同一映像的多个实例时您通常希望每个容器 （映像实例） 在不同主机服务器中运行或在不同的容错域中的 VM。

总而言之，容器在整个应用程序生命周期工作流中提供以下优点：隔离性、可移植性、灵活性、可伸缩性和可控性。 最重要的优点是可在开发和操作之间提供隔离。

>[!div class="step-by-step"]
>[下一页](what-is-docker.md)