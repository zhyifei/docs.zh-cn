---
title: 为 Azure 构建云本机 .NET 应用程序
description: 构建利用 Azure 的容器、微服务和无服务器功能的云本机应用程序的指南。
author: ardalis
ms.date: 04/23/2020
ms.openlocfilehash: 24d5c75fc5d2e5623892e8f83daea52553d13765
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507385"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="eefbe-103">为 Azure 构建云本机 .NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="eefbe-103">Architecting Cloud Native .NET Applications for Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![封面图像](./media/cover.png)

<span data-ttu-id="eefbe-105">发布者</span><span class="sxs-lookup"><span data-stu-id="eefbe-105">PUBLISHED BY</span></span>

<span data-ttu-id="eefbe-106">Microsoft 开发人员部门、.NET 和 Visual Studio 产品团队</span><span class="sxs-lookup"><span data-stu-id="eefbe-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="eefbe-107">Microsoft Corporation 的一个部门</span><span class="sxs-lookup"><span data-stu-id="eefbe-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="eefbe-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="eefbe-108">One Microsoft Way</span></span>

<span data-ttu-id="eefbe-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="eefbe-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="eefbe-110">版权所有 &copy; 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="eefbe-110">Copyright &copy; 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="eefbe-111">保留所有权利。</span><span class="sxs-lookup"><span data-stu-id="eefbe-111">All rights reserved.</span></span> <span data-ttu-id="eefbe-112">未经发布者书面许可，不得以任何形式或任何方式复制或传播本书中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="eefbe-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="eefbe-113">本书“按原样”提供，表达作者的观点和看法。</span><span class="sxs-lookup"><span data-stu-id="eefbe-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="eefbe-114">本书中表达的观点、看法和信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="eefbe-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="eefbe-115">本书中提及的一些示例仅用于说明，纯属虚构。</span><span class="sxs-lookup"><span data-stu-id="eefbe-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="eefbe-116">不存在任何实际关联或联系，请勿妄加推断。</span><span class="sxs-lookup"><span data-stu-id="eefbe-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="eefbe-117">Microsoft 和 https://www.microsoft.com 上“商标”网页列出的商标是 Microsoft 集团公司的商标。</span><span class="sxs-lookup"><span data-stu-id="eefbe-117">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="eefbe-118">Mac 和 macOS 是 Apple Inc. 的商标</span><span class="sxs-lookup"><span data-stu-id="eefbe-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="eefbe-119">Docker 的鲸鱼徽标是 Docker Inc. 的注册商标经许可方可使用。</span><span class="sxs-lookup"><span data-stu-id="eefbe-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="eefbe-120">所有其他标记和徽标均为其各自所有者的财产。</span><span class="sxs-lookup"><span data-stu-id="eefbe-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="eefbe-121">作者：</span><span class="sxs-lookup"><span data-stu-id="eefbe-121">Authors:</span></span>

> <span data-ttu-id="eefbe-122">Rob Vettor，Microsoft 首席云系统架构师/IP 架构师 ([thinkingincloudnative.com](http://thinkingincloudnative.com/about/)) </span><span class="sxs-lookup"><span data-stu-id="eefbe-122">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="eefbe-123">Steve "ardalis" Smith，[Ardalis.com](https://ardalis.com)  软件设计师及培训师</span><span class="sxs-lookup"><span data-stu-id="eefbe-123">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="eefbe-124">参与者和审阅者：</span><span class="sxs-lookup"><span data-stu-id="eefbe-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="eefbe-125">**Cesar De Torre**，Microsoft .NET 团队首席项目经理</span><span class="sxs-lookup"><span data-stu-id="eefbe-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="eefbe-126">Nish Anil，Microsoft .NET 团队高级项目经理 </span><span class="sxs-lookup"><span data-stu-id="eefbe-126">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="eefbe-127">Jeremy Likness，Microsoft .NET 团队高级项目经理 </span><span class="sxs-lookup"><span data-stu-id="eefbe-127">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="eefbe-128">Cecil Phillip，Microsoft 高级云大使 </span><span class="sxs-lookup"><span data-stu-id="eefbe-128">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="eefbe-129">详细了解 eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="eefbe-129">Learn more about eShopOnContainers</span></span>

<span data-ttu-id="eefbe-130">编辑：</span><span class="sxs-lookup"><span data-stu-id="eefbe-130">Editors:</span></span>

> <span data-ttu-id="eefbe-131">Maira Wenzel，Microsoft .NET 团队高级项目经理 </span><span class="sxs-lookup"><span data-stu-id="eefbe-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="eefbe-132">本指南的目标读者</span><span class="sxs-lookup"><span data-stu-id="eefbe-132">Who should use this guide</span></span>

<span data-ttu-id="eefbe-133">本指南的受众主要是对学习如何构建为云设计的应用程序感兴趣的开发人员、开发主管和架构师。</span><span class="sxs-lookup"><span data-stu-id="eefbe-133">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="eefbe-134">次级受众是计划选择是否使用云本机方法构建其应用程序的技术决策者。</span><span class="sxs-lookup"><span data-stu-id="eefbe-134">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="eefbe-135">如何使用本指南</span><span class="sxs-lookup"><span data-stu-id="eefbe-135">How you can use this guide</span></span>

<span data-ttu-id="eefbe-136">本指南首先定义云本机，并介绍使用云本机原则和技术构建的参考应用程序。</span><span class="sxs-lookup"><span data-stu-id="eefbe-136">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="eefbe-137">除了前两章，本书内容分成特定章节，集中讨论大多数云本机应用程序的共通主题。</span><span class="sxs-lookup"><span data-stu-id="eefbe-137">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="eefbe-138">可以跳转到以下任何章节，了解相关云本机方法：</span><span class="sxs-lookup"><span data-stu-id="eefbe-138">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="eefbe-139">数据和数据访问</span><span class="sxs-lookup"><span data-stu-id="eefbe-139">Data and data access</span></span>
- <span data-ttu-id="eefbe-140">通信模式</span><span class="sxs-lookup"><span data-stu-id="eefbe-140">Communication patterns</span></span>
- <span data-ttu-id="eefbe-141">缩放和可伸缩性</span><span class="sxs-lookup"><span data-stu-id="eefbe-141">Scaling and scalability</span></span>
- <span data-ttu-id="eefbe-142">应用程序复原能力</span><span class="sxs-lookup"><span data-stu-id="eefbe-142">Application resiliency</span></span>
- <span data-ttu-id="eefbe-143">监视和运行状况</span><span class="sxs-lookup"><span data-stu-id="eefbe-143">Monitoring and health</span></span>
- <span data-ttu-id="eefbe-144">标识和安全性</span><span class="sxs-lookup"><span data-stu-id="eefbe-144">Identity and security</span></span>
- <span data-ttu-id="eefbe-145">DevOps</span><span class="sxs-lookup"><span data-stu-id="eefbe-145">DevOps</span></span>

<span data-ttu-id="eefbe-146">本指南有 PDF 格式和在线版本。</span><span class="sxs-lookup"><span data-stu-id="eefbe-146">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="eefbe-147">欢迎随时将此文档或其在线版本的链接转发给你的团队，以确保对这些主题有共同的理解。</span><span class="sxs-lookup"><span data-stu-id="eefbe-147">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="eefbe-148">这些主题中的大多数都得益于对基本原则和模式的一致理解，以及与这些主题相关的决策所涉及的权衡。</span><span class="sxs-lookup"><span data-stu-id="eefbe-148">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="eefbe-149">本文档的目标是为团队及其领导提供所需的信息，使其能够为应用程序的体系结构、开发和托管作出明智的决策。</span><span class="sxs-lookup"><span data-stu-id="eefbe-149">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="eefbe-150">下一页</span><span class="sxs-lookup"><span data-stu-id="eefbe-150">Next</span></span>](introduction.md)
