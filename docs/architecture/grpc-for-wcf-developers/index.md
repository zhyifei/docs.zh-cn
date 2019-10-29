---
title: 适用于 WCF 开发人员的 ASP.NET Core gRPC - 适用于 WCF 开发人员的 gRPC
description: 待撰写
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6a5b4f6d0b47a272f7a753e22bfd61b06202944a
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919381"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a>适用于 WCF 开发人员的 ASP.NET Core gRPC

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

Docker 的鲸鱼徽标是 Docker Inc. 的注册商标经许可方可使用。

所有其他标记和徽标均为其各自所有者的财产。

作者:

> **Mark Rendle** -首席技术官 - [视觉对象重新编码](https://visualrecode.com)
>
> **Miranda Steiner** - 技术作者

编辑：

> **Maira Wenzel** - 资深内容开发人员 - Microsoft

## <a name="introduction"></a>介绍

TODO

## <a name="purpose"></a>目标

TODO

## <a name="who-should-use-this-guide"></a>本指南的目标读者

**更新此内容**

本指南面向的是使用 gRPC 服务将 .NET Framework 4 及更早版本的 WCF 解决方案迁移到 ASP.NET Core 3.0 感兴趣的 WCF 开发人员、开发主管和架构师。

## <a name="how-you-can-use-this-guide"></a>如何使用本指南

**更新此内容**

这是在 ASP.NET Core 3.0 中构建 gRPC 服务的简短介绍，还将 WCF 作为类似平台进行了介绍。 它解释了 gRPC 的原理，将每个概念与 WCF 的等效功能相关联，并提供了有关将现有 WCF 应用程序迁移到 gRPC 的指导。 对于具有 WCF 经验并想要学习通过 gRPC 构建新服务的开发人员来说，它也很有用。 可使用本指南中的示例应用程序作为项目模板或参考，并可自由复制和重用本书或示例中的代码。

请将本指南转发到团队中，这有助于确保对这些注意事项和机会的共同理解。 确保每个人使用共同的术语和基础原则工作，这有助于构建模式和做法的一致应用。

## <a name="references"></a>reference

- **gRPC 网站**  
  <https://grpc.io>
- **为服务器应用选择 .NET Core 或 .NET Framework**  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[下一篇](introduction.md)
