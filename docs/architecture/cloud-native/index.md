---
title: 为 Azure 构建云本机 .NET 应用程序
description: 构建利用 Azure 的容器、微服务和无服务器功能的云本机应用程序的指南。
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: 7f14a690d0153edc43f0ce7f4e91c9e9cd2c6858
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "71696776"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a>为 Azure 构建云本机 .NET 应用程序

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![封面图像](./media/cover.png)

发布者

Microsoft 开发人员部门、.NET 和 Visual Studio 产品团队

Microsoft Corporation 的一个部门

One Microsoft Way

Redmond, Washington 98052-6399

版权所有 © 2019 Microsoft Corporation

保留所有权利。 未经发布者书面许可，不得以任何形式或任何方式复制或传播本书中的任何内容。

本书“按原样”提供，表达作者的观点和看法。 本书中表达的观点、看法和信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。

本书中提及的一些示例仅用于说明，纯属虚构。 不存在任何实际关联或联系，请勿妄加推断。

Microsoft 和 https://www.microsoft.com 上“商标”网页列出的商标是 Microsoft 集团公司的商标。

Mac 和 macOS 是 Apple Inc. 的商标

Docker 的鲸鱼徽标是 Docker Inc. 的注册商标经许可方可使用。

所有其他标记和徽标均为其各自所有者的财产。

作者：

> **Steve "ardalis" Smith** - 软件设计师及培训师 - [Ardalis.com](https://ardalis.com)
>
> **Rob Vettor** - Microsoft - 首席云系统架构师/IP 架构师 - [RobVettor.com](https://robvettor.com)

参与者和审阅者：

> **Cesar De Torre**，Microsoft .NET 团队首席项目经理
>
> Microsoft .NET 团队高级项目经理 Nish Anil 

编辑：

> **Maira Wenzel**，Microsoft .NET 团队资深内容开发人员

## <a name="who-should-use-this-guide"></a>本指南的目标读者

本指南的受众主要是对学习如何构建为云设计的应用程序感兴趣的开发人员、开发主管和架构师。

次级受众是计划选择是否使用云本机方法构建其应用程序的技术决策者。

## <a name="how-you-can-use-this-guide"></a>如何使用本指南

本指南首先定义云本机，并介绍使用云本机原则和技术构建的参考应用程序。 除了前两章，本书内容分成特定章节，集中讨论大多数云本机应用程序的共通主题。 可以跳转到以下任何章节，了解相关云本机方法：

- 数据和数据访问
- 通信模式
- 缩放和可伸缩性
- 应用程序复原能力
- 监视和运行状况
- 标识和安全性
- DevOps

本指南有 PDF 格式和在线版本。 欢迎随时将此文档或其在线版本的链接转发给你的团队，以确保对这些主题有共同的理解。 这些主题中的大多数都得益于对基本原则和模式的一致理解，以及与这些主题相关的决策所涉及的权衡。 本文档的目标是为团队及其领导提供所需的信息，使其能够为应用程序的体系结构、开发和托管作出明智的决策。

>[!div class="step-by-step"]
>[下一页](introduction.md)
