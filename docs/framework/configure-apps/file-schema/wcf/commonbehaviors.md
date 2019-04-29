---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 73bf759fd3dfa87398aa74de93160a4ffce08eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704357"
---
# <a name="commonbehaviors"></a><span data-ttu-id="0c2b8-101">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="0c2b8-101">\<commonBehaviors></span></span>
<span data-ttu-id="0c2b8-102">`commonBehaviors` 节只能在 machine.config 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="0c2b8-102">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="0c2b8-103">它定义了名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="0c2b8-103">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="0c2b8-104">每个集合定义分别由所有 WCF 终结点和计算机上的服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="0c2b8-104">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="0c2b8-105">在 `endpointBehaviors` 中定义的行为只适用于客户端，在 `serviceBehaviors` 中定义的行为只适用于服务。</span><span class="sxs-lookup"><span data-stu-id="0c2b8-105">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="0c2b8-106">如果在 `commonBehaviors` 和 `behaviors` 节中都定义某行为，则 `behaviors` 节中的行为优先。</span><span class="sxs-lookup"><span data-stu-id="0c2b8-106">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
