---
title: '&lt;commonBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fceca3c1cf0cc980310b1c4fbf85f6bce5ad1a0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="ee97d-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="ee97d-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="ee97d-103">`commonBehaviors` 节只能在 machine.config 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="ee97d-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="ee97d-104">它定义了名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="ee97d-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="ee97d-105">每个集合分别定义计算机上所有 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="ee97d-105">Each collection defines behavior elements consumed by all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] endpoints and services on the machine respectively.</span></span> <span data-ttu-id="ee97d-106">在 `endpointBehaviors` 中定义的行为只适用于客户端，在 `serviceBehaviors` 中定义的行为只适用于服务。</span><span class="sxs-lookup"><span data-stu-id="ee97d-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="ee97d-107">如果在 `commonBehaviors` 和 `behaviors` 节中都定义某行为，则 `behaviors` 节中的行为优先。</span><span class="sxs-lookup"><span data-stu-id="ee97d-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
