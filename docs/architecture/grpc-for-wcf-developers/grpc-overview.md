---
title: 适用于 WCF 开发人员的 gRPC 概述-gRPC
description: 了解指导开发 gRPC 的原则集。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6980b473a6f9852a4e4f396355e98e2d3300cabe
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841587"
---
# <a name="grpc-overview"></a><span data-ttu-id="26892-103">gRPC 概述</span><span class="sxs-lookup"><span data-stu-id="26892-103">gRPC overview</span></span>

<span data-ttu-id="26892-104">查看上一章中的 WCF 和 gRPC 的 genesis 后，本章会考虑 gRPC 的一些主要功能，以及它们与 WCF 的比较方式。</span><span class="sxs-lookup"><span data-stu-id="26892-104">After looking at the genesis of both WCF and gRPC in the last chapter, this chapter will consider some of the key features of gRPC and how they compare to WCF.</span></span>

<span data-ttu-id="26892-105">ASP.NET Core 3.0 是 ASP.NET 的第一个版本，该版本本身支持 gRPC 作为第一类公民，由 Microsoft 团队共同提供 gRPC 的官方 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="26892-105">ASP.NET Core 3.0 is the first release of ASP.NET that natively supports gRPC as a first-class citizen, with Microsoft teams contributing to the official .NET implementation of gRPC.</span></span> <span data-ttu-id="26892-106">建议将其作为使用 .NET 生成分布式应用程序的最佳方法，该方法可与所有其他主要编程语言和框架互操作。</span><span class="sxs-lookup"><span data-stu-id="26892-106">It's recommended as the best approach for building distributed applications with .NET that can interoperate with all other major programming languages and frameworks.</span></span>

## <a name="key-principles"></a><span data-ttu-id="26892-107">关键原则</span><span class="sxs-lookup"><span data-stu-id="26892-107">Key principles</span></span>

<span data-ttu-id="26892-108">如第1章所述，Google 希望使用 HTTP/2 的引入来替换 Stubby，它的内部通用 RPC 基础结构。</span><span class="sxs-lookup"><span data-stu-id="26892-108">As discussed in chapter 1, Google wanted to use the introduction of HTTP/2 to replace Stubby, its internal, general purpose RPC infrastructure.</span></span> <span data-ttu-id="26892-109">基于 Stubby 的 gRPC 现在可以利用标准化，并将其适用性扩展到移动计算、云和物联网。</span><span class="sxs-lookup"><span data-stu-id="26892-109">gRPC, based on Stubby, now could take advantage of standardization and would extend its applicability to mobile computing, the cloud, and the Internet of Things.</span></span>

<span data-ttu-id="26892-110">为实现此目的，[云本机计算基础（CNCF）](https://www.cncf.io/)建立了一组可管理 gRPC 的原则。</span><span class="sxs-lookup"><span data-stu-id="26892-110">To achieve this, the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) established a set of principles that would govern gRPC.</span></span> <span data-ttu-id="26892-111">以下列表显示了最相关的列表，主要涉及到最大限度地提高可访问性和可用性：</span><span class="sxs-lookup"><span data-stu-id="26892-111">The following list shows the most relevant ones, which are mainly concerned with maximizing accessibility and usability:</span></span>

- <span data-ttu-id="26892-112">**免费和开放**–所有项目都应该是开放源代码，其中包含不会限制开发人员采用 gRPC 的授权。</span><span class="sxs-lookup"><span data-stu-id="26892-112">**Free and open** – all artifacts should be open source with licensing that doesn't constrain developers from adopting gRPC.</span></span>
- <span data-ttu-id="26892-113">**覆盖面和简单性**– gRPC 应在每个热门平台上可用，并可以轻松地在任何平台上构建。</span><span class="sxs-lookup"><span data-stu-id="26892-113">**Coverage and simplicity** – gRPC should be available across every popular platform and simple enough to build on any platform.</span></span>
- <span data-ttu-id="26892-114">**互操作性和联系性**–应能在任何网络上使用 gRPC，而不考虑带宽或延迟，使用广泛可用的网络标准。</span><span class="sxs-lookup"><span data-stu-id="26892-114">**Interoperability and reach** – it should be possible to use gRPC on any network, regardless of bandwidth or latency, using widely available network standards.</span></span>
- <span data-ttu-id="26892-115">"**常规用途" 和**"高性能" –在不影响性能的情况下，框架应可通过广泛使用的一系列使用情况来使用。</span><span class="sxs-lookup"><span data-stu-id="26892-115">**General purpose and performant** – the framework should be usable by as broad a range of use-cases as possible without compromising performance.</span></span>
- <span data-ttu-id="26892-116">**流式处理**–协议应为大型数据集或异步消息传送提供流式传输语义。</span><span class="sxs-lookup"><span data-stu-id="26892-116">**Streaming** – the protocol should provide streaming semantics for large data-sets or asynchronous messaging.</span></span>
- <span data-ttu-id="26892-117">**元数据交换**–协议允许与实际的业务数据分开处理非业务数据，如身份验证令牌。</span><span class="sxs-lookup"><span data-stu-id="26892-117">**Metadata exchange** – the protocol allow non-business data, such as authentication tokens, to be handled separately from actual business data.</span></span>
- <span data-ttu-id="26892-118">**标准化状态代码**–应降低错误代码的可变性，使错误处理决策更清晰，并且需要额外的更丰富的错误处理，则应提供一种机制来管理元数据交换。</span><span class="sxs-lookup"><span data-stu-id="26892-118">**Standardized status codes** – the variability of error codes should be reduced to make error handling decisions clearer and, where additional richer error handling is required, a mechanism should be provided for managing this within the metadata exchange.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="26892-119">[上一页](introduction.md)
>[下一页](approach.md)</span><span class="sxs-lookup"><span data-stu-id="26892-119">[Previous](introduction.md)
[Next](approach.md)</span></span>
