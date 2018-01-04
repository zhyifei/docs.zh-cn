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
ms.workload: dotnet
ms.openlocfilehash: 5fbe48bc3b6bc3c932abd52bcfb2d50dcc8ab4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-on-the-client"></a><span data-ttu-id="ab1a1-102">在客户端上调试</span><span class="sxs-lookup"><span data-stu-id="ab1a1-102">Debugging on the Client</span></span>
<span data-ttu-id="ab1a1-103">若要使用户更轻松地编写客户端应用程序你[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务，你可以添加[ \<serviceDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)服务为你的服务配置文件的行为。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-103">To make it easier for users to write client applications for your [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service, you can add the [\<serviceDebug>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) service behavior to the configuration file of your service.</span></span> <span data-ttu-id="ab1a1-104">此行为可用于发布帮助页，以及在返回到客户端的 SOAP 错误的详细信息中返回托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-104">This behavior can be used to publish help pages, and return managed exception information in the details of SOAP faults returned to the client.</span></span>
