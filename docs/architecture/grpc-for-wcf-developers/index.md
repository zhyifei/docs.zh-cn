---
title: 适用于 WCF 开发人员的 ASP.NET Core gRPC - 适用于 WCF 开发人员的 gRPC
description: 待撰写
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: dc39fc96e7154fb50acd0b65a58586b3fa12ab50
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696923"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="9e94d-103">适用于 WCF 开发人员的 ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="9e94d-103">ASP.NET Core gRPC for WCF Developers</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![封面图像](./media/cover.png)

<span data-ttu-id="9e94d-105">发布者</span><span class="sxs-lookup"><span data-stu-id="9e94d-105">PUBLISHED BY</span></span>

<span data-ttu-id="9e94d-106">Microsoft 开发人员部门、.NET 和 Visual Studio 产品团队</span><span class="sxs-lookup"><span data-stu-id="9e94d-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="9e94d-107">Microsoft Corporation 的一个部门</span><span class="sxs-lookup"><span data-stu-id="9e94d-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="9e94d-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="9e94d-108">One Microsoft Way</span></span>

<span data-ttu-id="9e94d-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="9e94d-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="9e94d-110">版权所有 © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9e94d-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="9e94d-111">保留所有权利。</span><span class="sxs-lookup"><span data-stu-id="9e94d-111">All rights reserved.</span></span> <span data-ttu-id="9e94d-112">未经发布者书面许可，不得以任何形式或任何方式复制或传播本书中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="9e94d-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="9e94d-113">本书“按原样”提供，表达作者的观点和看法。</span><span class="sxs-lookup"><span data-stu-id="9e94d-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="9e94d-114">本书中表达的观点、看法和信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="9e94d-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="9e94d-115">本书中提及的一些示例仅用于说明，纯属虚构。</span><span class="sxs-lookup"><span data-stu-id="9e94d-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="9e94d-116">不存在任何实际关联或联系，请勿妄加推断。</span><span class="sxs-lookup"><span data-stu-id="9e94d-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="9e94d-117">Microsoft 和 https://www.microsoft.com 上“商标”网页列出的商标是 Microsoft 集团公司的商标。</span><span class="sxs-lookup"><span data-stu-id="9e94d-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="9e94d-118">Docker 的鲸鱼徽标是 Docker Inc. 的注册商标经许可方可使用。</span><span class="sxs-lookup"><span data-stu-id="9e94d-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="9e94d-119">所有其他标记和徽标均为其各自所有者的财产。</span><span class="sxs-lookup"><span data-stu-id="9e94d-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="9e94d-120">作者:</span><span class="sxs-lookup"><span data-stu-id="9e94d-120">Author:</span></span>

> <span data-ttu-id="9e94d-121">**Mark Rendle** -首席技术官 - [视觉对象重新编码](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="9e94d-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="9e94d-122">**Miranda Steiner** - 技术作者</span><span class="sxs-lookup"><span data-stu-id="9e94d-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="9e94d-123">编辑：</span><span class="sxs-lookup"><span data-stu-id="9e94d-123">Editors:</span></span>

> <span data-ttu-id="9e94d-124">**Maira Wenzel** - 资深内容开发人员 - Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e94d-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="9e94d-125">介绍</span><span class="sxs-lookup"><span data-stu-id="9e94d-125">Introduction</span></span>

<span data-ttu-id="9e94d-126">TODO</span><span class="sxs-lookup"><span data-stu-id="9e94d-126">TODO</span></span>

## <a name="purpose"></a><span data-ttu-id="9e94d-127">目标</span><span class="sxs-lookup"><span data-stu-id="9e94d-127">Purpose</span></span>

<span data-ttu-id="9e94d-128">TODO</span><span class="sxs-lookup"><span data-stu-id="9e94d-128">TODO</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="9e94d-129">本指南的目标读者</span><span class="sxs-lookup"><span data-stu-id="9e94d-129">Who should use this guide</span></span>

<span data-ttu-id="9e94d-130">**更新此内容**</span><span class="sxs-lookup"><span data-stu-id="9e94d-130">**UPDATE THIS**</span></span>

<span data-ttu-id="9e94d-131">本指南的受众是对使用 gRPC 服务将 .NET 4 及更早版本的 WCF 解决方案迁移到 ASP.NET Core 3.0 感兴趣的 WCF 开发人员、开发主管和架构师。</span><span class="sxs-lookup"><span data-stu-id="9e94d-131">The audience for this guide is WCF developers, development leads, and architects who are interested in migrating WCF solutions on .NET 4 and earlier to ASP.NET Core 3.0 using gRPC services.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="9e94d-132">如何使用本指南</span><span class="sxs-lookup"><span data-stu-id="9e94d-132">How you can use this guide</span></span>

<span data-ttu-id="9e94d-133">**更新此内容**</span><span class="sxs-lookup"><span data-stu-id="9e94d-133">**UPDATE THIS**</span></span>

<span data-ttu-id="9e94d-134">这是在 ASP.NET Core 3.0 中构建 gRPC 服务的简短介绍，还将 WCF 作为类似平台进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="9e94d-134">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="9e94d-135">它解释了 gRPC 的原理，将每个概念与 WCF 的等效功能相关联，并提供了有关将现有 WCF 应用程序迁移到 gRPC 的指导。</span><span class="sxs-lookup"><span data-stu-id="9e94d-135">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="9e94d-136">对于具有 WCF 经验并想要学习通过 gRPC 构建新服务的开发人员来说，它也很有用。</span><span class="sxs-lookup"><span data-stu-id="9e94d-136">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="9e94d-137">可使用本指南中的示例应用程序作为项目模板或参考，并可自由复制和重用本书或示例中的代码。</span><span class="sxs-lookup"><span data-stu-id="9e94d-137">The sample application can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="9e94d-138">请将本指南转发到团队中，这有助于确保对这些注意事项和机会的共同理解。</span><span class="sxs-lookup"><span data-stu-id="9e94d-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="9e94d-139">确保每个人使用共同的术语和基础原则工作，这有助于构建模式和做法的一致应用。</span><span class="sxs-lookup"><span data-stu-id="9e94d-139">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="9e94d-140">reference</span><span class="sxs-lookup"><span data-stu-id="9e94d-140">References</span></span>

- <span data-ttu-id="9e94d-141">**gRPC 网站**</span><span class="sxs-lookup"><span data-stu-id="9e94d-141">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="9e94d-142">**为服务器应用选择 .NET Core 或 .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="9e94d-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="9e94d-143">下一篇</span><span class="sxs-lookup"><span data-stu-id="9e94d-143">Next</span></span>](introduction.md)
