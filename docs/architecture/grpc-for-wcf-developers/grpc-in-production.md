---
title: gRPC 在生产中-gRPC for WCF 开发人员
description: 在生产环境中运行 ASP.NET Core gRPC 应用程序
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 2baef7071ab47616a58346cebf131cf0ba89537a
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841593"
---
# <a name="grpc-in-production"></a><span data-ttu-id="c6c34-103">生产中的 gRPC</span><span class="sxs-lookup"><span data-stu-id="c6c34-103">gRPC in production</span></span>

<span data-ttu-id="c6c34-104">可以使用 Docker 和 Kubernetes 等新式平台，在 Windows、Linux 和容器中运行 ASP.NET Core 3.0 应用程序（包括 gRPC 服务）。</span><span class="sxs-lookup"><span data-stu-id="c6c34-104">ASP.NET Core 3.0 applications, including gRPC services, can be run on Windows, Linux, and in containers using modern platforms like Docker and Kubernetes.</span></span> <span data-ttu-id="c6c34-105">本章将探讨在生产中运行 gRPC 服务的各种选项，并查看监视和日志记录选项，以确保系统的最佳操作。</span><span class="sxs-lookup"><span data-stu-id="c6c34-105">This chapter will explore the various options for running your gRPC services in production, and look at monitoring and logging options to ensure the optimal operation of systems.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c6c34-106">[上一页](encryption.md)
>[下一页](self-hosted.md)</span><span class="sxs-lookup"><span data-stu-id="c6c34-106">[Previous](encryption.md)
[Next](self-hosted.md)</span></span>
