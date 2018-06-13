---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 0a9fab68ce240fc37d27c42d9feff969b97f93a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350317"
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="995b6-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="995b6-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="995b6-103">`commonBehaviors` 节只能在 machine.config 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="995b6-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="995b6-104">它定义了名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="995b6-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="995b6-105">每个集合定义分别使用的所有 WCF 终结点和在计算机上的服务行为元素。</span><span class="sxs-lookup"><span data-stu-id="995b6-105">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="995b6-106">在 `endpointBehaviors` 中定义的行为只适用于客户端，在 `serviceBehaviors` 中定义的行为只适用于服务。</span><span class="sxs-lookup"><span data-stu-id="995b6-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="995b6-107">如果在 `commonBehaviors` 和 `behaviors` 节中都定义某行为，则 `behaviors` 节中的行为优先。</span><span class="sxs-lookup"><span data-stu-id="995b6-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
