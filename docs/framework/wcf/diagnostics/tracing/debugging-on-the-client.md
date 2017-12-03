---
title: "在客户端上调试"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56f9ad05-ea1b-4ef6-85f2-890f7ed71567
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd942658229c7c70cf6a8b6bcac79f17a1a2db14
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="debugging-on-the-client"></a><span data-ttu-id="b40b8-102">在客户端上调试</span><span class="sxs-lookup"><span data-stu-id="b40b8-102">Debugging on the Client</span></span>
<span data-ttu-id="b40b8-103">若要使用户更轻松地编写客户端应用程序你[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务，你可以添加[ \<serviceDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)服务为你的服务配置文件的行为。</span><span class="sxs-lookup"><span data-stu-id="b40b8-103">To make it easier for users to write client applications for your [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service, you can add the [\<serviceDebug>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) service behavior to the configuration file of your service.</span></span> <span data-ttu-id="b40b8-104">此行为可用于发布帮助页，以及在返回到客户端的 SOAP 错误的详细信息中返回托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="b40b8-104">This behavior can be used to publish help pages, and return managed exception information in the details of SOAP faults returned to the client.</span></span>
