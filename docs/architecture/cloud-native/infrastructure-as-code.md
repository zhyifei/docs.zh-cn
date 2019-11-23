---
title: 基础结构即代码
description: 构建适用于 Azure 的云本机 .NET 应用 |基础结构即代码
ms.date: 06/30/2019
ms.openlocfilehash: 3957da68ac28774f899f49fb181a29c2435902f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841779"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="3cc1c-103">基础结构即代码</span><span class="sxs-lookup"><span data-stu-id="3cc1c-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="3cc1c-104">云本机应用程序倾向于使用各种极好的平台即服务（PaaS）组件。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-104">Cloud-native applications tend to make use of all sorts of fantastic platform as a service (PaaS) components.</span></span> <span data-ttu-id="3cc1c-105">在 Azure 等云平台上，这些组件可能包括存储、服务总线和 SignalR 服务等。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-105">On a cloud platform like Azure, these components might include things like storage, Service Bus, and the SignalR service.</span></span> <span data-ttu-id="3cc1c-106">随着应用程序变得更加复杂，使用的这些服务的数量可能会增长。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-106">As applications become more complicated, the number of these services in use is likely to grow.</span></span> <span data-ttu-id="3cc1c-107">正如持续交付如何破坏部署到环境的传统模型一样，更改的快速进度还打破了集中式 IT 组管理环境的模型。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-107">Just as how continuous delivery broke the traditional model of deploying to an environment manually, the rapid pace of change also broke the model of having a centralized IT group manage environments.</span></span>

<span data-ttu-id="3cc1c-108">构建环境既可以也可以自动进行。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-108">Building environments can, and should, also be automated.</span></span> <span data-ttu-id="3cc1c-109">很多人都可以轻松地了解各种工具。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-109">There's a wide range of well thought out tools that can make the process easy.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="3cc1c-110">Azure 资源管理器模板</span><span class="sxs-lookup"><span data-stu-id="3cc1c-110">Azure Resource Manager templates</span></span>

<span data-ttu-id="3cc1c-111">Azure 资源管理器模板是一种基于 JSON 的语言，用于定义 Azure 中的各种资源。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-111">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="3cc1c-112">基本架构如图11-10 所示。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-112">The basic schema looks something like Figure 11-10.</span></span>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

<span data-ttu-id="3cc1c-113">**图 11-10** -资源管理器模板的架构</span><span class="sxs-lookup"><span data-stu-id="3cc1c-113">**Figure 11-10** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="3cc1c-114">在此模板中，可能会在资源部分中定义一个存储容器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3cc1c-114">Within this template, one might define a storage container inside the resources section like so:</span></span>

```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

<span data-ttu-id="3cc1c-115">**图 11-11** -资源管理器模板中定义的存储帐户的示例</span><span class="sxs-lookup"><span data-stu-id="3cc1c-115">**Figure 11-11** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="3cc1c-116">模板可以参数化，以便可以将一个模板用于不同的设置来定义开发、QA 和生产环境。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-116">The templates can be parameterized so that one template can be reused with different settings to define development, QA, and production environments.</span></span> <span data-ttu-id="3cc1c-117">如果迁移到与较低环境不同的环境，这有助于消除意外情况。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-117">This helps eliminate surprises when migrating to a higher environment that is set up differently from the lower environments.</span></span> <span data-ttu-id="3cc1c-118">模板中定义的资源通常都是在 Azure 上的单个资源组中创建的（可以在单个资源管理器模板中定义多个资源组，但这种情况并不常见）。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-118">The resources defined in a template are typically all created within a single resource group on Azure (it's possible to define multiple resource groups in a single Resource Manager template but unusual).</span></span> <span data-ttu-id="3cc1c-119">这样，只需删除整个资源组即可轻松删除环境。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-119">This makes it very easy to delete an environment by just deleting the resource group as a whole.</span></span> <span data-ttu-id="3cc1c-120">成本分析还可以在资源组级别运行，从而可以快速评估每个环境的成本。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-120">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="3cc1c-121">GitHub 上的[Azure 快速入门模板](https://github.com/Azure/azure-quickstart-templates)项目中定义了多个示例模板，这些模板将在启动新模板或将其添加到现有模板时提供一段时间。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-121">There are many example templates defined in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub that will give a leg up when starting on a new template or adding to an existing one.</span></span>

<span data-ttu-id="3cc1c-122">可以通过多种方式运行资源管理器模板。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-122">Resource Manager templates can be run in a variety of ways.</span></span> <span data-ttu-id="3cc1c-123">最简单的方法是将它们粘贴到 Azure 门户中。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-123">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="3cc1c-124">对于实验部署，此方法非常简单。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-124">For experimental deployments, this method can be very quick.</span></span> <span data-ttu-id="3cc1c-125">它们还可以作为 Azure DevOps 中的生成或发布过程的一部分运行。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-125">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="3cc1c-126">有一些任务将利用连接到 Azure 运行模板。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-126">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="3cc1c-127">对资源管理器模板的更改以增量方式应用，这意味着，若要添加新资源，只需将其添加到模板。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-127">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="3cc1c-128">工具将处理当前资源组与模板中定义的所需资源组的比较。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-128">The tooling will handle diffing the current resource group with the desired resource group defined in the template.</span></span> <span data-ttu-id="3cc1c-129">然后，将创建或更改资源，使其与模板中定义的内容相匹配。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-129">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="3cc1c-130">Terraform</span><span class="sxs-lookup"><span data-stu-id="3cc1c-130">Terraform</span></span>

<span data-ttu-id="3cc1c-131">资源管理器模板的一个明显缺点是它们特定于 Azure 云。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-131">A perceived disadvantage of Resource Manager templates is that they are specific to the Azure cloud.</span></span> <span data-ttu-id="3cc1c-132">创建包含来自多个云的资源的应用程序是很罕见的，但是，如果企业依赖于工作正常运行时间，则支持多个云的成本可能值得。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-132">It's unusual to create applications that include resources from more than one cloud, but in cases where the business relies on spectacular uptime, the cost of supporting multiple clouds might be worthwhile.</span></span> <span data-ttu-id="3cc1c-133">如果有一种可跨每个云使用的模板化语言，则它还会使开发人员的技能更易于移植。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-133">If there were one templating language that could be used across every cloud, then it would also allow for developer skills to be much more portable.</span></span>

<span data-ttu-id="3cc1c-134">有多种技术可实现这一点。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-134">Several technologies exist which do just that!</span></span> <span data-ttu-id="3cc1c-135">该空间中最成熟的产品称为[Terraform](https://www.terraform.io/)。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-135">The most mature offering in that space is known as [Terraform](https://www.terraform.io/).</span></span> <span data-ttu-id="3cc1c-136">Terraform 支持每个主要的云播放器，如 Azure、Google Cloud Platform、AWS 和 AliCloud，并且还支持数十个次要玩家，如 Heroku 和 DigitalOcean。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-136">Terraform supports every major cloud player such as Azure, Google Cloud Platform, AWS, and AliCloud, and it also supports dozens of minor players such as Heroku and DigitalOcean.</span></span> <span data-ttu-id="3cc1c-137">它使用的简要 YAML 略有不同，而不是使用 JSON 作为模板定义语言。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-137">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="3cc1c-138">图11-12 中显示了一个示例 Terraform 文件，该文件与以前的资源管理器模板相同（图11-11）：</span><span class="sxs-lookup"><span data-stu-id="3cc1c-138">An example Terraform file that does the same as the previous Resource Manager template (Figure 11-11) is shown in Figure 11-12:</span></span>

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

<span data-ttu-id="3cc1c-139">**图 11-12** -资源管理器模板的示例</span><span class="sxs-lookup"><span data-stu-id="3cc1c-139">**Figure 11-12** - An example of a Resource Manager template</span></span>

<span data-ttu-id="3cc1c-140">当由于模板中的错误而无法部署资源时，Terraform 提供了合理的错误消息。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-140">Terraform does a better job of providing sensible error messages when a resource can't be deployed because of an error in the template.</span></span> <span data-ttu-id="3cc1c-141">这是一个区域，其中资源管理器模板有一些正在进行的挑战。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-141">This is an area where Resource Manager templates have some ongoing challenges.</span></span> <span data-ttu-id="3cc1c-142">还有一个非常方便的验证任务，可在生成阶段使用该任务来提前捕获模板错误。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-142">There's also a very handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="3cc1c-143">与资源管理器模板一样，可以使用命令行工具来部署 Terraform 模板。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-143">As with Resource Manager templates, there are command-line tools that can be used to deploy Terraform templates.</span></span> <span data-ttu-id="3cc1c-144">Azure Pipelines 中还提供了社区创建的任务，可以验证和应用 Terraform 模板。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-144">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="3cc1c-145">如果 "Terraform" 或 "资源管理器" 模板将有趣的值（如连接字符串）输出到新创建的数据库，则可以在生成管道中捕获这些值，并在后续任务中使用它们。</span><span class="sxs-lookup"><span data-stu-id="3cc1c-145">In the event that the Terraform or Resource Manager template outputs interesting values such as the connection string to a newly created database they can be captured in the build pipeline and used in subsequent tasks.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3cc1c-146">[上一页](devops.md)
>[下一页](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="3cc1c-146">[Previous](devops.md)
[Next](application-bundles.md)</span></span>
